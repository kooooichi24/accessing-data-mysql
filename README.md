# accessing-data-mysql
## 使い方
- インストール
    - git clone https://github.com/kooooichi24/accessing-data-mysql.git
    - cd accessing-data-mysql
- dockerでMySQLの環境構築
    - Docker-hubからMySQLのイメージをインストールする
        - docker pull mysql
    - インストールしたイメージから、コンテナを起動･作成する
        - docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d -p 3306:3306 mysql:latest
        - docker exec -it some-mysql bash
    - MySQLのコンテナにログインする
        - mysql -u root -p -h 127.0.0.1
- データベースを作成する
    - mysql> create database db_example; -- Creates the new database
    - mysql> create user 'springuser'@'%' identified by 'ThePassword'; -- Creates the user
    - mysql> grant all on db_example.* to 'springuser'@'%'; -- Gives all privileges to the new user on the newly created database
-