## Leanote Docker Image
All data is in /leanote/data volume. We can mount local data folder for this volume.
More details from this [wiki](https://github.com/leanote/leanote/wiki)

#### 1. Clone files:

```sh
git clone https://github.com/private-leanote/docker-leanote.git
```

#### 2. Create data folder

```
cd docker-leanote
mkdir -p ./leanote/data/{files,mongodb_backup,public/upload}
```

#### 3. Init configuration and routes file

```sh
git clone https://github.com/leanote-for-signle-user/leanote-conf.git ./leanote/conf
```

#### 4. Create the Stack which will include a MongoDB container and a Leanote one

```
docker-compose up -d
```

#### 5. Initialize database

```
docker exec -it leanote_server  mongorestore -h db -d leanote --dir /leanote/leanote_install_data
```

#### 6. Profit :-)

Once all the above steps are completed you can login using http://SERVER_IP:9000/login 

Credentials:

 - user: admin 
 - password: abc123 (please **CHANGE** it)

