ClearML XL Server
=================

Docker setup for ClearML server deployment.

## Usage

```
cd docker/
cp .env.example .env
```
and fill in the variables at your preference.

Then run `docker-compose up -d`.

Finally set correct permissions

```
source .env
sudo chown -R 1000:1000 ${CLEARML_ROOT_PATH}
sudo chmod og+wr -R ${CLEARML_ROOT_PATH}/clearml/data/redis
```


### Exposing with Nginx

todo

SSL can be added with certbot.

## Notes

- when configuring clearml.conf we need to manually change 8081 to 8085 in the fileserver URL. Alternatively you can use the `clearml.conf` file skeleton from this repo, and change only the credentials part in the api section.
