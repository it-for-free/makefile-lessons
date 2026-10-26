# Урок 5: длинную команду выносим в переменную
# и используем её в нескольких целях.

CONFIG_DIR = config
CAT_CONFIG = cat $(CONFIG_DIR)/app.conf

show:
	@$(CAT_CONFIG)

lines:
	@echo "Строк в конфиге:"
	@$(CAT_CONFIG) | wc -l
