# Урок 9: цветной вывод и export.
# export делает переменную переменной окружения - она видна
# внутри всех запускаемых команд. Коды цветов даёт утилита tput.

export cyan = `tput setaf 6`
export green = `tput setaf 2`
export yellow = `tput setaf 3`
export reset = `tput sgr0`

hello:
	@echo "${cyan}Привет!)${reset}"

done:
	@echo "${yellow}Внимание:${reset} почти готово"
	@echo "${green}Готово!${reset}"
