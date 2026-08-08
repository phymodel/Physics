# 周期公式

## 公式

$$
\boxed{
T=\dfrac{1}{f}
}
$$

## 位移和时间的测量

- 计时器：电磁打点计时器 $5\,\rm V$，电火花计时器 $220\,\rm V$，都是交流电，工作频率都是 50 $Hz$.
- 时间测量：周期等于频率的倒数 $T=\dfrac{1}{f}=\dfrac{1}{50\,\rm Hz}=0.02\,\rm s$.
- 位移测量：周期为 0.02，即每隔 0.02 打一个点，用刻度尺测量纸带点的位置.

## 设计交互场景

- 实体_计时器：3D场景所需的实体。
- 实体_时间测量：3D场景所需的实体。
- 实体_位移测量：3D场景所需的实体。

- 触发系统：3D场景交互所需的触发系统。

### 实体_计时器

```phymodel

Text()
.name("Timer")
.mesh(text: "计时器", extrusionDepth: 0.01, fontSize: 0.08)
.physic(mass: 0.1, staticFriction: 0.9, dynamicFriction: 0.75, restitution: 0.22, mode: .kinematic)
.material(red: 0.2, green: 0.8, blue: 1.0, opacity: 1, roughness: 0.5, metallic: 0.8)
.position(x: -0.5, y: 1.5, z: 0.0)

Text()
.name("TimeMeasurement")
.mesh(text: "时间测量", extrusionDepth: 0.01, fontSize: 0.08)
.physic(mass: 0.1, staticFriction: 0.9, dynamicFriction: 0.75, restitution: 0.22, mode: .kinematic)
.material(red: 0.2, green: 0.8, blue: 1.0, opacity: 1, roughness: 0.5, metallic: 0.8)
.position(x: 0.0, y: 1.5, z: 0.0)

Text()
.name("DisplacementMeasurement")
.mesh(text: "位移测量", extrusionDepth: 0.01, fontSize: 0.08)
.physic(mass: 0.1, staticFriction: 0.9, dynamicFriction: 0.75, restitution: 0.22, mode: .kinematic)
.material(red: 0.2, green: 0.8, blue: 1.0, opacity: 1, roughness: 0.5, metallic: 0.8)
.position(x: 0.5, y: 1.5, z: 0.0)

```

### 实体_时间测量

```phymodel

Latex()
.name("Frequency")
.mesh(width: 0.4, text: ¥¥
<center>
<span style="font-size: 80px;"> $f=50\,{\rm Hz}$
</span>
</center>
¥¥
)
.material(red: 1.0, green: 1.0, blue: 1.0, opacity: 0.999, roughness: 0.5, metallic: 0.8)
.physic(mass: 0.1, staticFriction: 0.9, dynamicFriction: 0.75, restitution: 0.22, mode: .kinematic)
.position(x: -0.06, y: 1.25, z: 0.0)

Latex()
.name("TFormula")
.mesh(width: 1.0, text: ¥¥
<center>
<span style="font-size: 90px;"> $T=\dfrac{1}{f}=\dfrac{1}{50\,{\rm Hz}}=0.02\,\rm s$
</span>
</center>
¥¥
)
.material(red: 1.0, green: 1.0, blue: 1.0, opacity: 0.999, roughness: 0.5, metallic: 0.8)
.physic(mass: 0.1, staticFriction: 0.9, dynamicFriction: 0.75, restitution: 0.22, mode: .kinematic)
.position(x: 0.0, y: 1.3, z: 0.0)

```

### 实体_位移测量

```phymodel

CAD()
.name("Box")
.mesh(commands: [
    "DEF box = PATH 0,0,0 X 0.01,0.001 -0.01,0.001 -0.01,-0.001 0.01,-0.001 EXT 1.0",
])
.material(red: 1.0, green: 1.0, blue: 1.0, opacity: 1, roughness: 0.3, metallic: 0.5)
.physic(mass: 0.5, staticFriction: 0.6, dynamicFriction: 0.4, restitution: 0.2, mode: .kinematic)
.position(x: -0.5, y: 1.1, z: 0.0)
.gesture(false)

Group(name: "CoordinateSystemX", position: (0.0, 1.1, 0.0), gesture: false) {
    Repeat(50) { i in
        CAD()
        .name("CoordinateSystemEllipsoid[i]")
        .mesh(commands: [
            "DEF box = PATH 0,0,0 Z 0.001,0.001 -0.001,0.001 -0.001,-0.001 0.001,-0.001 EXT 0.002",
        ])
        .material(red: 0.0, green: 0.0, blue: 0.0, opacity: 1, roughness: 0.5, metallic: 0.8)
        .physic(mass: 0.6, staticFriction: 0.6, dynamicFriction: 0.4, restitution: 0.2, mode: .kinematic)
        .position(x: -0.48 + (i * 0.02) * (i * 0.02), y: 0.0, z: 0.0)
        .gesture(false)
    }
}

```

### 触发系统

```phymodel



```
