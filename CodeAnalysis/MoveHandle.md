# MoveHandle

> 监听充当move  handle 的元素的 鼠标按下与松开的事件，给windw toggle 监听 鼠标移动事件，让目标元素随着鼠标移动而移动  

> 用到的几个js event 对象的属性e.type,  e.screenX ，和e.screenY    

> [e.pageX、e.clientX、e.screenX、e.offsetX的区别以及元素的一些CSS属性-blog](https://www.cnblogs.com/zhaixr/p/7026320.html)，
看完这篇博客后可以对e.pageX,e.clientX,e.screenX 几个属性画一个**解说图**， （ps渣渣，可以上手试试哦，I can）


```

/**
 * Initializes the given HTMLDomElement as the move handle for this DockingPanel.
 * When this element is clicked and dragged, this DockingPanel is moved.
//初始化给定的HTMLDomElement作为这个DockingPanel的move手柄。
//当这个元素被点击并拖动时，这个DockingPanel被移动。
 * @param {HTMLElement} mover - The DOM element that will act as the move handle.
 */
//@param {HTMLElement} mover 将充当move手柄的DOM元素
DockingPanel.prototype.initializeMoveHandlers = function (mover) {
    var x, y;             // 偏移量加对冲值，为目标元素动态的偏移量
    var lastX, lastY;     //始终记录鼠标移动后的位于屏幕的坐标
    var startX, startY;   //始终为鼠标按下时目标元素相对与父容器元素的偏移量
    var deltaX, deltaY;   //对冲值 ，从鼠标按下到松开移动期间，每次移动的屏幕坐标变化的动态累加值 
    var container = this.container;  // move handle 元素的容器元素，即被移动的元素  
    var self = this;

    // This gets scoped under window during the handleMove event handler
    function handleMove(e) {

        // 定义最小宽高，如果容器元素定义了最小宽度样式则获取样式值，否则取值自定义的最小值100
        var minWidth  = container.style.minWidth ? parseInt(container.style.minWidth) : self.kMinWdth,
            minHeight = container.style.minHeight ? parseInt(container.style.minHeight) : self.kMinHeight,

            // 获取move handle 元素的容器边界矩形 这是定义的方法 getContainerBoundingRect  ，目的返回父母的边界矩形容器。
            // 自定义方法中调用getBoundingClientRect，获取边界客户端矩形 
            // getBoundingClientRect用于获得页面中某个元素的左，上，右和下分别相对浏览器视窗的位置。
            // 
            // 此值为canvas的容器元素的矩形 
            parentRect = self.getContainerBoundingRect();
        // 纠正被移动元素的宽高？被移动元素的最大宽度样式存在，且实际宽度如果大于了定义的最大宽度则纠正宽度值为最大宽度
        // 这里的代码存在的意义.....意思是被移动元素的宽高可能动态改变嘛....?
        if (container.style.maxWidth && parseInt(container.style.width) > parseInt(container.style.maxWidth)) {
            container.style.width = container.style.maxWidth;
        }
        if (container.style.maxHeight && parseInt(container.style.height) > parseInt(container.style.maxHeight)) {
            container.style.height = container.style.maxHeight;
        }
         
        // 如果被移动元素的宽高小于最小宽高值则纠正其值为最小宽高值
        // 宽高动态变大可以理解，随着内容增多容器被撑高，可这里纠偏最小宽度的目的又是什么？
        // 其意义.....为了避免空内容造成容器元素塌陷不好看？
        if (parseInt(container.style.width) < minWidth) {
            container.style.width = minWidth + "px";
        }
        if (parseInt(container.style.height) < minHeight) {
            container.style.height = minHeight + "px";
        }

        // 兼容移动设备
        if (e.type === "touchmove") {
            e.screenX = e.touches[0].screenX;
            e.screenY = e.touches[0].screenY;
        }
        
        // 记录对冲值
        deltaX += e.screenX - lastX;
        deltaY += e.screenY - lastY;
        //改变偏移量
        x = startX + deltaX;
        y = startY + deltaY;
        
        //每次移动都获取目标元素的宽高值做甚？
        var wi = parseInt(container.style.width);
        var hi = parseInt(container.style.height);
    
        // 还有可能获取不到容器元素的宽高？所以从该元素边界客户端矩形中获取宽高值，所以这个宽高值在接下来的代码中很重要....
        if (isNaN(wi)) {
            wi = self.container.getBoundingClientRect().width;
        }
        if (isNaN(hi)) {
            hi = self.container.getBoundingClientRect().height;
        }
        
        //纠偏偏移量，左边和上边，让目标元素始终与父容器元素保持5像素的距离，同时不跑出去
        // check left, top
        if (x < 5)
            x = 0;

        if (y < 5)
            y = 0;
        
        // 哦，这个是组件内部的属性设置，取消停靠在右边和底部
        container.dockRight = false;
        container.dockBottom = false;
        
        //纠偏，右边和底部
        // check bottom, right
        // 把变量长的表达式放左边，代码会好看点的原因吗？
        // 当左偏移量加目标元素的宽度大于 父容器宽度，则停靠在右边，重新赋值x
        if (parentRect.width - 5 < x + wi) {
            x = parentRect.width - wi;
            container.dockRight = true;
        }

        if (parentRect.height - 5 < y + hi) {
            y = parentRect.height - hi;
            container.dockBottom = true;
        }
/*
        if (self.scrollContainer) {
            if (x == 0) {
                self.scrollContainer.classList.remove("right");
                self.scrollContainer.classList.add("left");
            }
            else {
                self.scrollContainer.classList.remove("left");
                self.scrollContainer.classList.add("right");
            }
        }
*/
       //改变样式，顺便把最大宽度和最小宽度给定义了 
        container.style.left = x + "px";
        container.style.top = y + "px";
        // 父矩形框的宽高固定，xy为动态值，动态定义目标元素的 最大宽高值的意义何在？
        // 避免目标元素的内容跑出容器，看不到内容？
        container.style.maxWidth  = (parentRect.width - x) + "px";
        container.style.maxHeight = (parentRect.height - y) + "px";

        //TODO: check for right side
        //TODO: handle docking and bounds check against the canvas element

        lastX = e.screenX;
        lastY = e.screenY;
        
        //这里还没有完，移动了个元素，然后通知其他覆盖元素
        self.onMove(e, x, y);
    }

    function handleUp(e) {
        // 移除window上监听的鼠标移动，鼠标松开的监听，
        window.removeEventListener('mousemove', handleMove);
        window.removeEventListener('mouseup', handleUp);
        window.removeEventListener('touchmove', handleMove);
        window.removeEventListener('touchend', handleUp);
        self.onEndMove(e, x, y);
    }

    function handleDown(e) {
        // 兼容移动设备
        if (e.type === "touchstart") {
            e.screenX = e.touches[0].screenX;
            e.screenY = e.touches[0].screenY;
        }

        // 记录鼠标在屏幕中的坐标值
        lastX = e.screenX;
        lastY = e.screenY;
        // 重置对冲值
        deltaX = 0;
        deltaY = 0;

        // Save the current panel position relative to its parent container.
        // 保存当前面板相对于其父容器的位置。
        //
        startX = self.container.offsetLeft;
        startY = self.container.offsetTop;
       
        // 监听window鼠标移动和鼠标松开的事件
        window.addEventListener('mousemove', handleMove, false);
        window.addEventListener('mouseup', handleUp, false);
        window.addEventListener('touchmove', handleMove, false);
        window.addEventListener('touchend', handleUp, false);
        
        //阻止事件的默认行为
        e.preventDefault();

        self.onStartMove(e, startX, startY);
    }

    // We'll keep track of the mousedown event listener as this one is always active.
    // The mousemove and mouseup listeners above are temporary so we don't need to track them.
    //我们将跟踪mousedown事件监听器，因为它总是处于活动状态。
    //上面的“mousemove”和“mouseup”监听器是临时的，所以我们不需要跟踪它们。
    // 这里始终监听move handle元素的 鼠标按下的事件 
    self.addEventListener(mover, 'mousedown', handleDown);
    self.addEventListener(mover, 'touchstart', handleDown);
};
```
