# Skillfactory Data Science Hackaton 2023

Репозиторий хакатона в рамках первого семестра магистерской программы
Skillfactory и МФТИ "Науки о данных".

*Задача проекта* — улучшить опыт от посещения музеев, городов или
новых мест с помощью информационных технологий.

*Цель проекта* — сделать посещение людьми музеев, городов или новых 
мест интересным, информативным и комфортным.

## Предлагаемое решение

Для реализации цели предлагается приложение по распознаванию эмоций
с помощью модели машинного обучения (нейронной сети).  

Приложение по распознаванию эмоций может быть полезно в музеях по
нескольким причинам.  

Например, анализируя, какие эмоции получают посетители от тех или иных
экспонатов, музей может адаптировать свои
коллекции таким образом, чтобы добиться желаемого отклика.  

Кроме того, посетителям можно будет предоставить персонализированные
рекомендации, на основе их эмоциональных предпочтений.  

Обучение нейронной сети выполнено на основе
[этого набора данных Kaggle](https://www.kaggle.com/datasets/sujaykapadnis/emotion-recognition-dataset).  

Для запуска [jupyter-ноутбука](./hackaton.ipynb), выполняющего обучение
модели, его необходимо скачать и распаковать в директорию с ноутбуком.  

Обученные модели сохраняются, начиная с 15й эпохи, в папку `~/data/torch`,
ещё необходимо создать заранее.  

Уже обученную таким образом модель можно скачать
[здесь](https://drive.google.com/file/d/1cZaV8ab__-jepbpBx2gtjUWeRXeEn-a6/view).  

Для запуска обученной модели необходимо скачать и запустить
[браузерное приложение](https://github.com/aniyur/facial-emotion-recognition):  

Клонировать репозиторий с помощью `git clone https://github.com/aniyur/facial-emotion-recognition.git`.

Указать в переменной окружения `MODEL_FILE` путь к файлу модели.
Например, в системе `Linux` так: `export MODEL_FILE=/some/path/to/your/model_file.th`.

Далее запустить бэк-приложение, которое будет использовать модель для
распознавания эмоций (предполагается, что команды
выполняются из папки с вышеупомянутым репозиторием,
который предлагалось клонировать):  
```
cd server
pip install -r requirements.txt
uvicorn main:app --reload
```

Далее запустить браузерное приложение так (после запуска откроется
браузер, понадобится дать доступ к камере):  
```
cd emotion-recognition
npm install
npm start
```

После этого необходимо подождать несколько секунд, пока оба приложения
запустятся, в браузере можно будет посмотреть
распознавание эмоций человека, который смотрит в веб-камеру.  
