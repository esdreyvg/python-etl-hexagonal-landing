# python-etl-hexagonal-landing

**Un framework ETL production-ready con arquitectura hexagonal real.**
Conecta cualquier fuente de datos a Parquet en minutos — sin tocar código.

---

## ¿Qué problema resuelve?

La mayoría de pipelines ETL en Python terminan siendo scripts monolíticos:
lógica de negocio mezclada con pandas, queries hardcodeadas, sin tests,
imposibles de mantener.

Este kit te da una **base arquitectónica correcta desde el primer día**:
dominio puro, ports bien definidos, infraestructura intercambiable y
configuración 100% declarativa por JSON.

---
## Estructura del proyecto

```
python-etl-hexagonal/
├── src/
│   ├── core/                    # Dominio puro — sin dependencias externas
│   │   ├── domain/              # Entities, Value Objects, Exceptions
│   │   └── ports/               # Interfaces: Extractor, Transformer, Loader
│   ├── application/             # Casos de uso: RunPipeline, ValidateSchema
│   └── infrastructure/          # Implementaciones concretas
│       ├── extractors/          # CSV, Excel, REST, PostgreSQL
│       ├── transformers/        # PandasTransformer
│       ├── loaders/             # ParquetLoader
│       ├── config/              # PipelineConfig + PipelineBuilder
│       └── notifications/       # SmtpNotifier
├── tests/
│   ├── unit/                    # 20+ tests — sin DB, sin archivos
│   └── integration/             # End-to-end CSV → Parquet
├── config/                      # 3 ejemplos JSON listos
├── docs/                        # Arquitectura, extensión, fault-tolerance
├── main.py                      # CLI con argparse
├── Makefile                     # run, test, lint, coverage
└── SETUP.md                     # Guía de instalación paso a paso
```

---

## Licencia

Uso personal y comercial permitido. No redistribuir como template.

---
## Link de Compra
https://esdrey.gumroad.com/l/python-etl-hexagonal-kit