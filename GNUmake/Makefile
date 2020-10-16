.PHONY: help

#1.Компиляций
exe: main.o foo.o
	@gcc main.o foo.o -o exe

main.o: main.c foo.h
	@gcc -c main.c -o main.o

foo.o: foo.c
	@gcc -c foo.c -o foo.o

#2.Тестовый запуск
test: exe
	@./exe
	@if [ $$? -ne 0 ]; \
    then \
        echo "Error"; \
        false;\
    else \
    	echo "Success"; \
    	true;\
    fi;


#3.Установка
install: exe
	@mkdir dir;cp exe dir/exe

#4.Создание дистрибутива
zip:
	@zip -o pkg.zip Makefile foo.c foo.h main.c docfile

#5.Создание документации
doc:
	doxygen docfile

#6.Очистка проекта
#без удаления некоторых файлов
clear:
	@rm *.o
#полная очистка 
clean:
	@rm -r dir *.o pkg.zip exe documentation

#7.Справка
help:
	@echo Use one of the following
	@echo "exe (default)\ntest\ninstall\nclear\nclean\nwc\nhelp"

#8.Запуск скриптов
wc:
	@wc foo.c

.DEFAULT:
	@echo ERROR: wrong target
	@make help