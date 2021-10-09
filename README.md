heroku login
heroku create flask-face-detection-thuan
heroku git:remote -a flask-face-detection-thuan
heroku buildpacks:add --index 1 https://github.com/heroku/heroku-buildpack-apt
git push heroku HEAD:master


- Tạo app flask có file main.py (trước khi push chuyển 127.0.0.1 thành 0.0.0.0)
    VD: app.run(host='0.0.0.0', port=5000, debug=True)
- Thêm file Procfile có nội dung:
    web: gunicorn main:app --preload
    # main ở đây là main.py
- Cài đặt pipreqs để tạo file requirements.txt cần thiết
    pip install pipreqs
- Tạo file requirements.txt
    pipreqs --encoding=utf8 .
- Thêm 'gunicorn' vào file requirements.txt vừa tạo
- Đưa lên github
    + Tạo repo trên github
    + Gõ trong terminal
        git init
        git add .
        git commit -m "init"
        git remote add origin https://github.com/Ngocpt0920/flask_heroku.git ( URL repo )
        git push --set-upstream origin master

- Login heroku, tạo app, push
    heroku login (Đăng nhập)
    heroku create flask-heroku-ngoc (Tạo)
    heroku git:remote -a flask-heroku-ngoc (chuyển remote git)
    git push heroku HEAD:master

- Lần sau đổi code cần push lại:
    git add .
    git commit -m "change ..."
    git push
    git push heroku HEAD:master