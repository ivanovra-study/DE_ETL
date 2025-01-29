# Запуск Apache NiFi с использованием Docker Compose и выполнение домашних заданий

Этот репозиторий содержит конфигурацию для запуска Apache NiFi с помощью Docker Compose. NiFi используется для обработки данных, полученных с IoT-устройств, которые измеряют температуру. В рамках домашнего задания были выполнены преобразования данных из датасета [Temperature Readings from IoT Devices](https://www.kaggle.com/datasets/atulanandjha/temperature-readings-iot-devices).

### Описание задания
1. Вычислить 5 самых жарких и самых холодных дней за весну.
2. Отфильтровать данные по условию `out/in = in`.
3. Преобразовать поле `noted_date` в формат `'yyyy-MM-dd'` с типом данных `date`.
4. Очистить температуру по 5-му и 95-му процентилю.

## Структура репозитория

- **`nifi-files/`**: Директория для хранения файлов NiFi, монтируется в контейнер.
- **`docker-compose.yaml`**: Конфигурация Docker Compose для запуска NiFi.
- **`start.sh`**: Скрипт для запуска контейнера.
- **`stop.sh`**: Скрипт для остановки контейнера.
- **`.gitignore`**: Файл для исключения ненужных файлов из Git.
- **`README.md`**: Описание проекта и инструкции по использованию.

## Требования

- Установленный Docker и Docker Compose.
- Доступ к интернету для загрузки образа Apache NiFi.

## Как использовать

1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/ivanovra-study/DE_ETL.git
   cd DE_ETL
   ```

2. **Скачайте датасет:**
   Датасет с показаниями температуры IoT-устройств можно скачать по ссылке:  
   [Скачать датасет](https://www.kaggle.com/datasets/atulanandjha/temperature-readings-iot-devices?resource=download)

   После скачивания поместите файлы датасета в директорию `nifi-files/`.

3. **Запустите NiFi:**
   Для запуска контейнера выполните:
   ```bash
   ./start.sh
   ```

   NiFi будет доступен по адресу:  
   [https://localhost:8443/nifi](https://localhost:8443/nifi)

   Логин: `admin`  
   Пароль: `ctsBtRBKHRAx69EqUghvvgEvjnaLjFEB`

4. **Остановите NiFi:**
   Для остановки контейнера выполните:
   ```bash
   ./stop.sh
   ```
