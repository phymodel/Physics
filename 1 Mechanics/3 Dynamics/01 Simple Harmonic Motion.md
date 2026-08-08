# 简谐运动

$x(t)=A\cos(\omega t+\varphi)$

## 设计交互场景

- 实体：3D场景所需的实体。
- 触发系统：3D场景交互所需的触发系统。

### 实体

```phymodel

LissajousFigure()
.name("lissajousFigure1")
.mesh(frequencyX: 2, frequencyY: 3, phase: 0, depth: 0.5)
.physic(mass: 0.9, staticFriction: 0.6, dynamicFriction: 0.4, restitution: 0.2, mode: .dynamic)
.material(red: 0.5, green: 0.2, blue: 1.0, opacity: 1, roughness: 0.5, metallic: 0.8)
.position(x: 0.0, y: 1.5, z: -1.5)

```

### 触发系统

```phymodel


```
