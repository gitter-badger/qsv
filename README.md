Process .csv files with a SQL like syntax.

*Work in Progress*

*Currently supports SELECT statements*

![qsv demo session](https://s3-us-west-2.amazonaws.com/s.cdpn.io/496585/qsv.gif)

```bash
npm install qsv -g
```

Or if you're using yarn
```bash
yarn global add qsv
```
For files with headers:
```bash
qsv -p "./path/to/my/file.csv" -h
```

For files without headers:
```bash
qsv -p "./path/to/my/file.csv"
```
After loading the file you will get into REPL mode, indicated by the QSV> prompt.
In REPL mode you can use SQL Queries against your .csv file.

Examples:

```bash
SELECT * FROM table
```

```bash
SELECT column1, column2 FROM table
```

table is just a placeholder, you don't need to specify something that makes sense, just don't leave it blank.
column1 and column2 are examples for the header fields.

If your .csv file doesn't have headers omit the -h option.
Your table will receive enumerated headers in memory, so you can query it like this:

```bash
SELECT 0, 1 FROM table
```

Options

| Option | Verbose Version | Description                                 |
| ------ | --------------- | ------------------------------------------- |
| -h     |                 | Indicate that the file to parse has headers |
| -d     |                 | Specifiy the delimiter of your file.        |