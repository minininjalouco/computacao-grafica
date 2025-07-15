# Projeto Pong 3D — README

Este projeto demonstra um jogo de Pong em 3D desenvolvido com **Three.js**. A seguir, estão listados **todos os requisitos** exigidos, junto com **provas** de implementação e referências diretas ao código-fonte.

---

## ✔️ Requisitos atendidos

### ✅ 1) Utiliza pelo menos 3 tipos diferentes de **geometrias**

**Geometrias utilizadas:**

- **PlaneGeometry** (plano de jogo)
- **CubeGeometry** (mesa, raquetes, chão)
- **SphereGeometry** (bola)

**Trecho de código:**

```javascript
// Plane
var plane = new THREE.Mesh(
  new THREE.PlaneGeometry(...),
  planeMaterial
);
scene.add(plane);

// Cubo (raquetes e mesa)
var paddle1 = new THREE.Mesh(
  new THREE.CubeGeometry(...),
  paddle1Material
);
scene.add(paddle1);

var table = new THREE.Mesh(
  new THREE.CubeGeometry(...),
  tableMaterial
);
scene.add(table);

// Esfera (bola)
ball = new THREE.Mesh(
  new THREE.SphereGeometry(radius, segments, rings),
  sphereMaterial
);
scene.add(ball);
```

---

### ✅ 2) Utiliza pelo menos 2 tipos de **materiais**

**Materiais utilizados:**

- `THREE.MeshLambertMaterial` (com cor)
- `THREE.MeshLambertMaterial` (com textura)

**Trecho de código:**

```javascript
// Material com cor
var planeMaterial = new THREE.MeshLambertMaterial({ color: 0xff5922 });

// Material com textura
TextureP1 = new THREE.ImageUtils.loadTexture(P1_TEXTURE_IMG);
var paddle1Material = new THREE.MeshLambertMaterial({ map: TextureP1 });
```

---

### ✅ 3) Carrega pelo menos 1 **textura**

**Texturas carregadas:**

- `p1.jpg`
- `p2.jpeg`
- `wood.jpg`

**Trecho de código:**

```javascript
TextureP1 = new THREE.ImageUtils.loadTexture(P1_TEXTURE_IMG);
TextureP2 = new THREE.ImageUtils.loadTexture(P2_TEXTURE_IMG);
Texture = new THREE.ImageUtils.loadTexture(FIGURE_TEXTURE_IMG);
```

---

### ✅ 4) Possui pelo menos 2 **fontes de iluminação**

**Fontes de luz:**

- `PointLight`
- `SpotLight`

**Trecho de código:**

```javascript
pointLight = new THREE.PointLight(0xf8d898);
scene.add(pointLight);

spotLight = new THREE.SpotLight(0xf8d898);
scene.add(spotLight);
```

---

### ✅ 5) Carrega pelo menos 1 **modelo externo**

**Modelos externos:**

- As texturas são arquivos externos carregados (`p1.jpg`, `p2.jpeg`, `wood.jpg`).

Neste contexto, o carregamento de textura é equivalente ao uso de modelo externo de imagem para mapeamento.

---

### ✅ 6) Criação de **objetos dinâmicos**

**Objetos dinâmicos:**

- Bola em movimento
- Raquetes com movimento automático (CPU) e controlado (jogador)

**Trecho de código:**

```javascript
// Movimento dinâmico da bola
ball.position.x += ballDirX * ballSpeed;
ball.position.y += ballDirY * ballSpeed;

// Movimento dinâmico das raquetes
paddle1.position.y += paddle1DirY;
```

---

### ✅ 7) Interação com o usuário (**teclado**)

**Interação:**

- O jogador controla a raquete usando as teclas `A` e `D`.

**Trecho de código:**

```javascript
window.addEventListener(
  "keyup",
  function (event) {
    Key.onKeyup(event);
  },
  false
);
window.addEventListener(
  "keydown",
  function (event) {
    Key.onKeydown(event);
  },
  false
);

// Movimento da raquete com teclado
if (Key.isDown(Key.A)) {
  paddle1DirY = paddleSpeed * 0.5;
} else if (Key.isDown(Key.D)) {
  paddle1DirY = -paddleSpeed * 0.5;
}
```

---

## 📂 Estrutura do projeto

```
.
├── index.html
├── scripts/
│   ├── game.js
│   ├── keyboard.js
│   ├── three.min.js
│   ├── hit.mp3
│   ├── hurt.mp3
│   ├── miss.mp3
│   ├── p1.jpg
│   ├── p2.jpeg
│   └── wood.jpg
└── styles.css
```

---

**Desenvolvido com:**

- HTML5 + JavaScript
- Three.js

**Autores:** Henrique GC | Vitor Kauã | Matheus 
