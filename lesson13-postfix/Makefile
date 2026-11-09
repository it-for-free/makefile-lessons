# Урок 13: постфиксы-обёртки - семейство целей .prod
# и рекурсивный вызов make из make.
# Попробуйте: make build.prod, make show.prod, make rebuild.prod

APP_ENV ?= dev
CONFIG_DIR = config
OUT = out/app.conf

export cyan = `tput setaf 6`
export green = `tput setaf 2`
export reset = `tput sgr0`

CMDS = build show rebuild
PROD = $(addsuffix .prod,$(CMDS))

.PHONY: help build show rebuild clean $(PROD)

help:
	@echo "${cyan}Сборка конфига${reset}, доступные команды: \
	     \n ${green}build${reset} - собрать конфиг (APP_ENV=prod) \
	     \n ${green}show${reset} - показать собранный конфиг \
	     \n ${green}rebuild${reset} - пересобрать с нуля \
	     \n ${green}clean${reset} - удалить собранное \
	     \n ${green}build.prod${reset} (и др.) - те же команды для prod \
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

# Семейство обёрток: build.prod, show.prod, rebuild.prod.
# $(@:.prod=) срезает постфикс - получаем имя исходной команды.
$(PROD):
	@$(MAKE) --no-print-directory $(@:.prod=) APP_ENV=prod
