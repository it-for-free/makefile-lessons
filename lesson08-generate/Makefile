# Урок 8: генерация конфига из переменных.
# >  - записывает строку в файл (создаёт новый),
# >>  - дописывает строку в конец файла.
# Попробуйте: make generate, make show, make clean

APP_NAME = my-app
PORT = 8080
DEBUG = true
CONFIG = config/app.conf

generate:
	@mkdir -p config
	@echo "# конфиг приложения $(APP_NAME)" > $(CONFIG)
	@echo "port = $(PORT)" >> $(CONFIG)
	@echo "debug = $(DEBUG)" >> $(CONFIG)
	@echo "Создан файл $(CONFIG)"

show:
	@cat $(CONFIG)

clean:
	@rm -f $(CONFIG)
	@echo "Удалён файл $(CONFIG)"
