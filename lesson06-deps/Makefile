# Урок 6: зависимости - цели из списка выполняются ДО основной.
# Порядок видно по номерам в сообщениях:
#   make build    -> 1, 2
#   make rebuild  -> 0, 1, 2, 3

build: prepare
	@echo "2. Собираем конфиг out/app.conf"
	@echo "# собрано командой make" > out/app.conf

prepare:
	@echo "1. Готовим каталог out/"
	@mkdir -p out

rebuild: clean build
	@echo "3. Пересборка завершена"

clean:
	@echo "0. Чистим каталог out/"
	@rm -rf out
