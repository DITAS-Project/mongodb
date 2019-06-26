# DITAS SDK MongoDB instance

## Running instructions
1. Create the two paths on the host, one for the data, and another one for the configuration. For example: `/mongo/data/db` and `/mongo/etc/mongo`.
2. Inside the last path (`/mongo/etc/mongo/`) put the `mongodb.conf` file of this repo.
3. Run the container setting a root username and password:

```
docker run -p 50010:27017 --restart unless-stopped -v /mongo/data/db:/data/db -v /mongo/etc/mongo:/etc/mongo -e MONGO_INITDB_ROOT_USERNAME=YOUR_USERNAME -e MONGO_INITDB_ROOT_PASSWORD=YOUR_PASSWORD -d mongo:3.4 --config /etc/mongo/mongodb.conf
```