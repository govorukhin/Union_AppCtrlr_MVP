В этом проекте приведён более реалистичный пример программы. В ней есть и разные страницы экрана, и взаимодействие с источником данных, и настройки которые будучи установленными в одном месте, влияют на другие места (и всё это без глобальных переменных!).

#### «Проблема», решаемая программой:
Допустим, есть неограниченное количество счётчиков, передающих показания в реальном времени. И нужно отслеживать графики их показаний. Но интерес представляют графики не всех сразу счётчиков, а комбинации некоторых из них.

#### Описание программы:
Есть «сервер», который собирает показания счётчиков раз в единицу времени, записывает их в «хранилище данных», и выдаёт диаграммам таблицу с последними N записями из хранилища.  
Счётчики можно добавлять и удалять.  
На добавляемых(и удаляемых по нажатию за крестик) вкладках располагаются диаграммы. В каждой из них можно выставить отображение нужных счётчиков.


#### Примерная архитектура программы:
В классе Program происходит создание объектов, и их передача в класс ApplicationController.
В котором:
* Задаются предстартовые действия и условия выключения программы.
* Визуальные объекты передаются в класс, реализующий работу графического интерфейса.
* Объекты, созданные в Program, передаются классам-связям настраивающим их взаимодействие.
