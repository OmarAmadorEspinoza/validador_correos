# Validador de correos

![CI](https://github.com/OmarAmadorEspinoza/validador_correos/actions/workflows/ci.yml/badge.svg)

Proyecto de la actividad **U4ACT03 - DevOps con Python y GitHub Actions**. Es una función en Python que valida correos electrónicos, con pruebas automáticas (pytest) y un pipeline de CI/CD en GitHub Actions.

## Qué hace

La función `es_correo_valido(correo)` devuelve `True` solo si el correo cumple tres reglas:

- Tiene exactamente una arroba (@).
- Tiene algo escrito antes de la arroba (usuario).
- El dominio, después de la arroba, contiene un punto.

## Estructura del proyecto

    validador_correos/
    ├── validador.py          # función es_correo_valido
    ├── test_validador.py     # pruebas con pytest
    ├── requirements.txt      # dependencias (pytest)
    └── .github/workflows/
        └── ci.yml            # workflow de GitHub Actions

## Cómo ejecutarlo en tu computadora

    git clone https://github.com/OmarAmadorEspinoza/validador_correos.git
    cd validador_correos
    python3 -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    pytest -v

## Pipeline CI/CD

El workflow se activa con cada `push` a la rama `main` y tiene dos jobs:

| Job | Qué hace |
| --- | --- |
| `test` | Descarga el código, instala Python 3.12 y las dependencias, y ejecuta pytest. |
| `deploy` | Simula el despliegue a producción. Usa `needs: test`, así que solo corre si las pruebas pasaron. |

Si una prueba falla, `test` queda en rojo y `deploy` no se ejecuta.

## Evidencia

Documento de la actividad con capturas, respuestas y bitácora: [ver PDF](U4ACT03_DevOps_con_python_AmadorEspinoza_GTIR246.pdf)

## Autor

Omar Manuel Amador Espinoza
Actividad U4ACT03 - Infraestructura de redes de datos
