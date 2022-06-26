# bible

Bible data from https://github.com/scrollmapper/bible_databases

- `encode.py` encodes the data to vectors
- `search.py` performs semantic search on the vectors

## Format

- embeddings.parquet has b,c,v,e
- books.parquet has b,n
- text.parquet has b,c,v,t

- b int (book id)
- c int (chapter)
- v int (verse)
- t string (text)
- e list<float> (embedding)
- n string (book name)

```bash
python encode.py --text t_web.csv --books key_english.csv --dir web
```

## Building the data

```bash
curl -O https://raw.githubusercontent.com/scrollmapper/bible_databases/master/csv/t_web.csv
curl -O https://raw.githubusercontent.com/scrollmapper/bible_databases/master/csv/key_english.csv
python encode_scrollmapper.py --text t_web.csv --books key_english.csv --dir web
```
