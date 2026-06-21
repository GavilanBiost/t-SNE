# t-SNE: teoría y buenas prácticas

Material de apoyo al hilo de LinkedIn sobre PCA vs t-SNE: de la teoría al código, sin atajos.

## Contenido

| Archivo | Descripción |
|---|---|
| `t-SNE.Rmd` | Tutorial en R (`Rtsne` + `ggplot2`): simulación de datos, preprocesado, barrido de perplejidad y visualización comparativa. |
| `t-SNE.html` / `t-SNE.pdf` | Versiones renderizadas del Rmd, listas para leer sin necesidad de ejecutar nada. |
| `tsne.ipynb` | Versión equivalente en Python (`scikit-learn` + `seaborn`), con las mismas secciones que el Rmd. |

## De qué va

Ambos cuadernos parten del mismo dataset simulado (3 grupos x 50 variables, con estructura de clúster conocida) y recorren los mismos pasos:

1. Fijar la semilla antes de cualquier paso estocástico.
2. Eliminar duplicados y escalar los datos como paso de preprocesado independiente.
3. Reducir dimensionalidad con PCA antes de t-SNE — en R viene integrado en `Rtsne()`, en Python hay que hacerlo a mano con `sklearn.decomposition.PCA`, ya que `scikit-learn` no lo incluye dentro de `TSNE`.
4. Comparar varios valores de perplejidad sobre los mismos datos.
5. Visualizar los resultados y dejar por escrito lo que conviene no olvidar: las distancias entre clústeres no significan nada, t-SNE es para explorar y no para inferir, etc.

## Requisitos

**R**
```r
install.packages(c("Rtsne", "ggplot2"))
```

**Python**
```bash
pip install scikit-learn pandas seaborn matplotlib
```

## Uso

- Abre `t-SNE.Rmd` en RStudio y haz *Knit*, o ejecútalo celda a celda.
- Abre `tsne.ipynb` en Jupyter o VS Code y ejecuta las celdas en orden.

Ambos están pensados como punto de partida: sustituye el dataset simulado por tu propia matriz de muestras x variables (genes, metabolitos, biomarcadores...) y el resto del flujo se mantiene igual.

## Licencia

Apache-2.0. Ver [LICENSE](LICENSE).
