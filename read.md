### transform

``` html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>复习transform</title>
    <style type="text/css">
    *{margin:0;padding:0;}
    .box{width:100px;height:100px;background:url("image/mf1.png");
    background-size:100%;margin:100px auto;transform:translateY(100px) rotate(45deg)}

    /* transform 中的rotate 默认是沿着z轴旋转,(把屏幕当成一个平面,垂直于这个平面的就是z轴),
    如果改为rotateX(45deg),沿着x轴旋转和沿着y轴旋转都是3d,默认的是2d,所以达不到3d的效果 */
    </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>

```

#####初步实现3d需要设置的一些属性:

> - 1.实现3d 变形效果,需要给当前元素的舞台设置一个视距perspective:1000px;

> - 2.transform-style:preserve-3d;

> - 3.根据需求设置transform-origin:设置旋转元素的基点位置.默认基准点为x轴,y轴,z轴的交叉点.

>  transform-origin:x y z;

> 1.x 轴基准点的值:left(0%),center(50%) ,right(100%)或者百分比,默认是50%.
> 2.y 轴基准点的值:top(0%),center(50%) ,bottom(100%)或者百分比,默认是50%.
> 3.z 轴基准点的值:0;(x,y,z三轴交集点为0)

在设置基点的时候x轴以物体的宽为标准,物体宽的左顶点为left,宽的一半为center,宽的右顶点为right.

在设置基点y轴的时候同x轴的准则.
