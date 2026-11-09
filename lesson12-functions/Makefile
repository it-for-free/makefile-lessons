# Урок 12: функции make - обработка списков значений.
# Список - это слова в переменной, разделённые пробелами.
# Попробуйте: make list

CONFIG_DIR = config
FILES = base.conf dev.conf prod.conf
CMDS = build show rebuild

list:
	@echo "Было:      $(CMDS)"
	@echo "Суффикс:   $(addsuffix .prod,$(CMDS))"
	@echo "Префикс:   $(addprefix $(CONFIG_DIR)/,$(FILES))"
	@echo "Без .conf: $(FILES:.conf=)"
