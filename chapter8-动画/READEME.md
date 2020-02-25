## 动画

### 过渡

过渡（transition），通过过渡可以指定一个属性发生变化时的切换方式，通过过渡可以实现一些非常好的效果，提升用户体验。

#### 设置的属性

`transition-property`：指定要执行过渡的属性，多个属性间用`,`隔开，如果所有的属性都需要过渡，就使用`all`关键字，大部分的属性都支持过渡效果，注意过渡必须是从一个有效值到另一个有效值的变化。

`transition-duration`指定过渡效果的持续时间，时间单位：秒 毫秒。

`transition-timing-function`：过渡的时序函数，指定的过渡的执行方式，可选值：`ease linear ease-in ease-out ease-in-out`，分别是默认值（先加速后减速），线性（匀速），加速运动，减速运动，先加速再减速，也可以通过`cubic-bezier()`来指定时序函数，还可以通过`steps()`分步执行过渡效果。

`transition-delay`：过渡效果的时延。

### 动画

动画和过渡类似，都是可以实现一些动态的效果，不同的是过渡需要在某个属性发生变化时才会触发，动画可以自动触发动态效果。

要设置一个动画效果，必须设置一个关键帧，关键帧设置了动画执行的每一个步骤。

```css
.box{
	width: 100px;
	height: 100px;
	background-color: red;
	/* 指定要对当前元素生效的关键帧的名字 */
	animation-name: myKeyframe;
	/* 设置持续时间 */
	animation-duration: 4s;
    
}

/* 设置一个关键帧 */
@keyframes myKeyframe{
/* 开始，相当于0% */
from{
	margin-left: 0px;
}

/* 结束，相当于100% */
to{
	margin-left: 700px;
	}
}
```

### 变形transform

#### 平移

通过设置`transform`属性可以让元素平移，可选值有：`translateX() translateY() translateZ()`，分别向`x y z`轴方向平移，可以指定具体像素值，也可以使用百分比。

通过平移，可以让没有明确指定大小的元素在其包含块内居中：

```css
div{
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
}
```

z轴平移，调整的是元素距离人眼的效果，z轴平移属于立体效果（近大远小），默认情况下网页是不支持透视的，如果需要支持透视，要设置网页的视距，一般在html中设置：

```css
html{
   perspective: 800px; 
}
```

#### 旋转，平移和旋转的组合

`rotateX() rotateY() rotateZ()`可以让元素分别绕`x y z`轴进行旋转，通过组合平移和旋转操作，可以做出很多很炫的效果。

#### 缩放

通过设置`scaleX() scaleY() scaleZ()`三个函数来对元素进行一个缩放，一般情况下只对`x y`两个方向上进行一个缩放。