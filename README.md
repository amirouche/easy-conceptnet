# easy-conceptnet

`easy-conceptnet` wants to be the easiest way to interact with
[conceptnet semantic network](https://conceptnet.io/).

## Cookbook

### Getting started quickly

```
git clone https://github.com/amirouche/easy-conceptnet/
cd easy-conceptnet
make database-download
./easy-conceptnet serve 8888
```

In another console try:

```
curl http://127.0.0.1:8888/api/
```

Look at the last section of this file to know which routes are
available.

### Building your own database

```
git clone https://github.com/amirouche/easy-conceptnet/
cd easy-conceptnet
make download-conceptnet
./easy-conceptnet index conceptnet-assertions-5.7.0.csv
```

It takes a couple of hours to index the whole file, please be patient!

## Documentation

### `GET /api/`

Display a banner with the version number

### `GET /api/c/{{ lang }}/{{ label }}`

Retrieve all the relations of the concept that is named `/c/{{ lang
}}/{{ label }}`. For instance, you can try the following:

```
curl http://127.0.0.1:8000/api/c/fr/concept`.
```

### `GET /api/fuzzy-search/{{ label }}`

Try to match `label` with a known concept.

For instance, you can try the following:

```
curl http://127.0.0.1/api/fuzzy-search/concpt
```
