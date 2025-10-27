# DeepACO / ACO — Reproducción en TSP (20/100/500)

Reproducción y análisis de **DeepACO** y **ACO** sobre instancias del **Traveling Salesman Problem (TSP)**.  
Este repositorio acompaña el reporte técnico: incluye instrucciones de instalación, guía de ejecución, organización de archivos y notas de reproducibilidad.

> Paper base: *DeepACO: Neural-enhanced Ant Systems for Combinatorial Optimization* (NeurIPS 2023).  
> Código base: repositorio oficial de DeepACO (modificaciones mínimas documentadas en el reporte).

---

## 📁 

```
.
├─ tsp/
│  ├─ aco.py
│  ├─ net.py
│  ├─ utils.py
│  └─ __init__.py
│  └─ test.ipynb
│  └─ train.ipynb
├─ README.md
```
---

##  Requisitos

- **Python 3.8.20**
- **PyTorch** (CPU o CUDA)
- **PyTorch Geometric (PyG)**
- NumPy, Matplotlib
- d2l` para animaciones/monitoreo


> **GPU (CUDA):** instala la build de Torch compatible con tu versión de CUDA y, luego, PyG según su guía oficial.

---

## Cómo correr los experimentos

### 1) aco.py
- En este archivo se retiene el algoritmo de ACO con sus parametros.
- Ejecuta

### 2) net.py
- Este tiene la red neuronal. 
- Ejecutar.

### 3) train.ipynb
- Abre `train.ipynb`.
- Selecciona `device="cpu"` (o `"cuda"` si tienes GPU compatible).
- Ejecuta las celdas de **entrenamiento** de la red sobre el algoritmo.

### 4) test.ipynb
- Ejecuta los bloques, aqui es donde cambias parametros como nodos o cantidad de hormigas para el problema.
---

## Figuras y tablas del informe

Este repositorio almacena los recursos usados en el reporte:

- **Reproducibilidad por tamaño** (TSP20, TSP100, TSP500) y sus respectivos resultados.
```

> En el informe LaTeX se usó redondeo a **5 decimales**.

---

##  Reproducibilidad

- **Presupuesto**: compara por el mismo **número de evaluaciones T** (1,10,20,30,40,50,100).
- **Dispositivo**: CPU por defecto; documenta si usas GPU (modelos/tiempos pueden cambiar).
- **Versionado**: registra versiones de librerías y comandos exactos ejecutados.

---

## Resultados de referencia (los usados en el informe)

**TSP20 (DeepACO, CPU)**  
- Repo: 3.92767 (T=1) → 3.85062 (T=100)  
- Modificado: idéntico por T (a 5 decimales); tiempo total ≈ **886.46 s** vs **915.16 s** (−3.1%)

**TSP100 (ACO, CPU)**  
- Repo: 13.63478 (T=1) → 9.55358 (T=100)  
- Modificado: 13.65005 → 9.56497 (**Δ** ≤ 0.12%); tiempo total ≈ **2759.84 s** vs **2697.08 s** (+2.33%)

> Pueden variar levemente por hardware/semillas.

---

##  Problemas comunes

- **PyTorch/PyG incompatibles**: instala primero Torch (CPU o CUDA), luego PyG compatible.
- **Pesos preentrenados** (si aplican): usa `map_location="cpu"` si corres sin GPU.
---

## 🙏 Agradecimientos

A los autores de DeepACO por el repositorio original y a la comunidad de PyTorch/PyG por sus herramientas.

Este repositorio es una reproducción del trabajo original de:

- Ye, Haoran; Wang, Jiarui; Cao, Zhiguang; Liang, Helan; Li, Yong.  
  *DeepACO: Neural-enhanced Ant Systems for Combinatorial Optimization (NeurIPS 2023).*  

Repositorio original: <https://github.com/henry-yeh/DeepACO.git>  
Todo el crédito por la idea y el código base es de sus autores; este repositorio solo documenta nuestra reproducción y comparaciones.
