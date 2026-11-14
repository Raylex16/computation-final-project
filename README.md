# Proyecto Final — Horario del Programa de Ingeniería de Sistemas (Equipo01)

Solución de la instancia pública `UCTP-IS-PUB` del problema de asignación de horarios universitarios
(UCTP): a cada bloque de clase se le asigna una franja y un salón sin violar ninguna restricción dura
(H1–H7) y minimizando la penalización de las restricciones blandas (S1–S6).

## Resultado

| Semilla | Factible | Penalización P | Detalle |
|---|---|---|---|
| 20 | Sí (H1–H7 = 0) | **27** | S4 = 25, S6 = 2, resto en 0 |

Las 10 semillas ejecutadas terminan factibles con P entre 27 y 33. Ejecución completa: menos de 4 minutos.

## Método

1. **Greedy "más restringido primero":** cada bloque va a la franja y salón factibles de menor costo incremental.
2. **Búsqueda local (recocido simulado):** mover bloque, intercambiar franjas, cadena de Kempe entre dos franjas
   y cambio de salón, siempre sobre horarios factibles y con costo incremental O(1).

No se usan solucionadores (OR-Tools, PuLP, etc.); solo la biblioteca estándar, `pandas`, `matplotlib` y `graphviz`.

## Estructura

```
Solucion_Equipo01.ipynb        Notebook con todo el código, resultados y respuestas
instancia_publica.json         Datos de la instancia (entregados por el profesor)
resultados/
  solucion_publica.json        Mejor solución en el formato de entrega
  horario.html                 Horario interactivo, generado por la celda V5 del notebook
Solucion_Equipo01.html         Copia del notebook ejecutado, para verlo sin Jupyter
requirements.txt               Dependencias de Python
```

## Cómo ejecutarlo

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate    |    Linux/macOS: source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook Solucion_Equipo01.ipynb
```

Luego **Kernel → Restart & Run All**. El notebook vuelve a generar `resultados/solucion_publica.json`
y `resultados/horario.html`, y muestra el horario interactivo dentro de la propia salida de la celda V5.

> El diagrama de flujo usa `graphviz`, que además del paquete de Python necesita el programa Graphviz
> instalado en el sistema (Windows: `winget install graphviz`; Ubuntu: `sudo apt install graphviz`;
> macOS: `brew install graphviz`).

## Integrantes

| Código | Nombre |
|---|---|
| 160005011 | Johan Sebastian Forero Agudelo |
| 160005004 | Santiago Barrera Meza |
| 160005010 | Jesus Gregorio Delgado |
