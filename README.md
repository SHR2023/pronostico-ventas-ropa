# Pronóstico de Ventas de Ropa de Mujer por Zona

Proyecto grupal — Caso de analítica de datos, Ciencia de Datos, Pontificia Universidad Javeriana.

Autores: Sharid Rodríguez, Juan Davis Manosalva, Laura Catalina Ariza, Juan García Diaz.

## Problema de negocio

Aura Chic, un detallista colombiano de moda y joyería por catálogo, necesita anticipar la demanda de ropa de mujer a nivel zonal para optimizar la asignación de inventario, catálogos y campañas comerciales. El objetivo del proyecto fue construir un modelo predictivo de las ventas anuales de ropa de mujer por zona y entender qué variables comerciales y operativas tienen mayor impacto sobre la demanda.

## Metodología

El proyecto siguió la metodología **CRISP-DM** de principio a fin:

- **Business & Data Understanding:** análisis PESTLE, Fuerzas de Porter y SWOT del sector moda/catálogo en Colombia; definición de objetivos de negocio y de minería de datos; análisis exploratorio univariado y multivariado sobre 1,600 observaciones zonales.
- **Data Preparation:** limpieza (corrección de errores de codificación, winsorización de outliers por regla de Tukey) e ingeniería de variables extensa: transformaciones logarítmicas, splines lineales truncados, términos polinómicos, interacciones de dos y tres variables, ratios de intensidad comercial y un índice compuesto de marketing — resultando en ~80 variables predictoras.
- **Modeling:** comparación sistemática entre **Stepwise OLS** (criterios AIC y BIC) y **LASSO** (penalización L1), seleccionando en cada iteración el modelo con menor RMSE en validación cruzada de 10 folds.
- **Evaluation:** el modelo final —Stepwise OLS con criterio BIC— alcanzó un RMSE de validación cruzada de **~10,441 COP**, con mejora progresiva a lo largo de las rondas de modelado.
- **Deployment:** estrategias de pronóstico zonal para planeación de inventario, priorización comercial por demanda esperada, y fortalecimiento del servicio al cliente (la variable con mayor correlación con las ventas).

## Resultados

| Métrica | Valor |
|---|---|
| RMSE (CV-10, modelo final) | ~10,441 COP |
| Técnica ganadora | Stepwise OLS (criterio BIC) |
| Variable más correlacionada con ventas | Nivel de servicio al cliente (r = 0.53) |

## Contenido del repositorio

- `Caso_1_Aprendizaje_de_Maquina.pdf` — reporte completo con la metodología CRISP-DM.
- Notebook/script con el desarrollo del modelo (limpieza, ingeniería de variables, comparación de modelos).

## Herramientas

R · MASS · caret · glmnet (LASSO) · validación cruzada de 10 folds
