# Урок 11: финальный проект - сборка конфига из частей.
# base.conf + оверлей окружения (dev или prod) -> out/app.conf.
# Ключи оверлея перебивают значения из базового файла.
#
#   $@ - цель, $< - первый исходник, $^ - все исходники

APP_ENV ?= dev
CONFIG_DIR = config
OUT = out/app.conf

export cyan = `tput setaf 6`
export green = `tput setaf 2`
export reset = `tput sgr0`

# help, build и др. - не файлы, а просто имена команд:
# без .PHONY цель с именем существующего файла считалась бы
# "уже собранной" (попробуйте убрать эту строку и создать
# файл с таким именем)
.PHONY: help build show rebuild clean

help:
	@echo "${cyan}Сборка конфига${reset}, доступные команды: \
	     \n ${green}build${reset} - собрать конфиг (окружение: APP_ENV=prod) \
	     \n ${green}show${reset} - показать собранный конфиг \
	     \n ${green}rebuild${reset} - пересобрать с нуля \
	     \n ${green}clean${reset} - удалить собранное \
	"

$(OUT): $(CONFIG_DIR)/base.conf $(CONFIG_DIR)/$(APP_ENV).conf
	@mkdir -p out
	@cat $^ > $@
	@echo "Собрано: ${green}$@${reset} (APP_ENV=$(APP_ENV))"

build: $(OUT)

show: build
	@cat $(OUT)

rebuild: clean build

clean:
	@rm -f $(OUT)
	@echo "Удалён файл $(OUT)"
