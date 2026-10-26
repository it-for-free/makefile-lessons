# Урок 10: цель-файл - make сравнивает время правки файлов
# и пересобирает цель только если исходник новее результата.
#   $@ - имя цели (out/app.conf)
#   $< - первый исходник (config/base.conf)
# Попробуйте дважды: make out/app.conf
# Затем: make change и снова make out/app.conf

out/app.conf: config/base.conf
	@mkdir -p out
	@echo "Пересобираю: $< -> $@"
	@cat $< > $@

change:
	@touch config/base.conf
	@echo "base.conf изменён"
