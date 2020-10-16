SUBDIRS = src doc

test: all
	@src/foo
	@if [ $$? -ne 0 ]; \
    then \
        echo "Error"; \
        false;\
    else \
    	echo "Success"; \
    	true;\
    fi;

wc:
	@wc src/foo.c

help:
	@echo "1.компиляция проекта (make)"	
	@echo "2.тестовый запуск проекта (make test)"
	@echo "3.установка скомпилированного проекта (make install)"
	@echo "4.создание дистрибутива проекта (make dist)"
	@echo "5.создание документации ±"
	@echo "6.очистка проекта без удаления некоторых файлов и полная очистка (make clean | make distclean)"
	@echo "8.справка об использовании файла сборки (make help)"
	@echo "9.запуск внешних скриптов и утилит (make wc)."


.DEFAULT:
	@echo ERROR: wrong target
	@make help