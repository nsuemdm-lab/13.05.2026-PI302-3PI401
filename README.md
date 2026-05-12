# datagen-go: Synthetic Data Generator

A flexible, Go-based tool for generating synthetic datasets and mutating existing ones based on statistical profiles.

## Overview

`datagen-go` is designed to create realistic datasets for testing, machine learning, and performance benchmarking. It analyzes sample data to build statistical profiles and then generates new data that follows the same distributions.

## Key Features

- **Generative Mode**: Creates entirely new datasets based on CSV samples.
- **Dimensional Mode**: Mutates existing datasets by adding, updating, or deleting rows while maintaining statistical consistency.
- **Anomaly Injection**: Inject specific patterns like statistical spikes, seasonal patterns, trend shifts, and multi-column correlations.
- **Pipeline Architecture**: Streaming data processing through chained channels (Generator → Anomaly → Writer).
- **Graceful Shutdown**: Signal handling (`SIGTERM`/`SIGINT`) and context-based cancellation for all pipeline stages.
- **Error Resilience**: Panic recovery, error propagation, and per-dataset result reporting.
- **Extended Distributions**: Normal (default), Poisson, Exponential, and Log-Normal — configurable per-column via YAML.
- **Worker Pool**: Configurable concurrency limit via `generator_workers` in config to control resource usage.
- **Extensibility**: Modular architecture for adding new generators, mutators, and anomaly types.

## Quick Start

1. **Configure**: Define your datasets in `config.yaml`.
2. **Build**: `go build -o datagen cmd/datagen/main.go`
3. **Run**: `./datagen -config config.yaml`

For more details, see [Detailed Description](meta_project/datagen._go.md) and [Development Roadmap](meta_project/ROADMAP.md).

---

# datagen-go: Генератор синтетических данных

Гибкий инструмент на языке Go для генерации синтетических наборов данных и мутации существующих на основе статистических профилей.

## Обзор

`datagen-go` предназначен для создания реалистичных наборов данных для тестирования, машинного обучения и оценки производительности. Он анализирует исходные данные для построения статистических профилей, а затем генерирует новые данные, следующие тем же распределениям.

## Ключевые особенности

- **Генеративный режим**: Создает полностью новые наборы данных на основе CSV-образцов.
- **Дивизиональный (размерный) режим**: Мутирует существующие наборы данных путем добавления, обновления или удаления строк, сохраняя статистическую согласованность.
- **Инъекция аномалий**: Позволяет внедрять специфические паттерны — статистические всплески, сезонные паттерны, сдвиги трендов и многостолбцовые корреляции.
- **Конвейерная архитектура**: Потоковая обработка данных через цепочку каналов (Generator → Anomaly → Writer).
- **Graceful Shutdown**: Обработка сигналов (`SIGTERM`/`SIGINT`) и отмена на основе context для всех стадий конвейера.
- **Отказоустойчивость**: Recovery от паники, распространение ошибок и поотчётность по каждому датасету.
- **Расширенные распределения**: Нормальное (по умолчанию), Пуассона, экспоненциальное и логнормальное — настраиваются для каждой колонки через YAML.
- **Параллелизм**: Обработка нескольких задач по генерации данных с настраиваемым лимитом конкурентности через `generator_workers`.
- **Расширяемость**: Модульная архитектура для добавления новых генераторов, мутаторов и типов аномалий.

## Быстрый старт

1. **Настройка**: Определите наборы данных в `config.yaml`.
2. **Сборка**: `go build -o datagen cmd/datagen/main.go`
3. **Запуск**: `./datagen -config config.yaml`

Для получения дополнительной информации см. [Подробное описание](meta_project/datagen._go.ru.md) и [План развития](meta_project/ROADMAP.ru.md).
