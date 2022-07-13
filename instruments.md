### kubernetes

#### Установка

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

or 

`brew install kubectl`

#### Установка

```bash
mkdir .kube
cd .kube
touch config
```

[kns/ktx](https://github.com/blendle/kns)


### goose
```bash
goose create вставить_название_что_делаешь sql
goose postgres "user=user dbname=db_name sslmode=disable host=addr password=pass" status
```
