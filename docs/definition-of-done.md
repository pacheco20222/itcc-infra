# Definition of Done (DoD) - IT Command Center

Para que un User Story, Feature o Bugfix sea considerado "Terminado" (Done) y pueda ser integrado a la rama `main` o pasar a producción, debe cumplir obligatoriamente con los siguientes criterios:

## 1. Código y Arquitectura
* El código compila sin errores ni warnings críticos en el entorno local (Docker/WSL).
* Se ha mantenido o mejorado la legibilidad del código siguiendo los estándares del proyecto.
* **[REGLA DE SEGURIDAD] Toda funcionalidad que exponga un endpoint HTTP debe validarse con prueba de integración desde un origen cross-domain para asegurar la correcta configuración de políticas CORS.**

## 2. Aseguramiento de Calidad (QA)
* Las pruebas locales pasan exitosamente.
* No existen bugs de severidad Alta o Crítica (Showstoppers) abiertos y asociados a la rama actual.
* Para microservicios de IA: Se ha verificado que la inferencia de los modelos (DistilBERT/Llama 3) no exceda el tiempo de timeout establecido en el Frontend.

## 3. Gestión de Configuración y CI/CD
* El código está versionado en el repositorio correspondiente (`itcc-frontend`, `itcc-backend-core`, o `itcc-ai-services`).
* Se ha abierto un Pull Request (PR) y no tiene conflictos de "merge" con la rama principal.
* Los pipelines de Integración Continua (GitHub Actions) se ejecutan sin errores (Status: Green).

## 4. Documentación
* Los cambios en los esquemas de bases de datos (Supabase) están reflejados en la documentación técnica.
* El README del servicio ha sido actualizado si se añadieron nuevas variables de entorno (.env).
