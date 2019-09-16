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
curl http://127.0.0.1:8888/api
```

Look at the last section of this file to know which routes are
available.

### Building your own database

```
git clone https://github.com/amirouche/easy-conceptnet/
cd easy-conceptnet
./easy-conceptnet index conceptnet-assertions-5.7.0.csv
```

It takes a couple of hours to index the whole file, please be patient!

## Documentation

### `GET /api/`

Display a banner with the version number

### `GET /api/lookup/c/{{ lang }}/{{ label }}`

Retrieve all the relations where the given concept that is named
`/c/{{ lang }}/{{ label }}` is the source. For instance, you can try
the following:

```
curl http://127.0.0.1:8000/api/lookup/c/fr/concept`.
```

It will return tab-separated values (tsv).

### `GET /api/reverse/c/{{ lang }}/{{ label }}`

Retrieve all the relations where the given concept that is named
`/c/{{ lang }}/{{ label }}` is the target. For instance, you can try
the following:

```
curl http://127.0.0.1:8000/api/reverse/c/fr/concept`.
```

It will return tab-separated values (tsv).
