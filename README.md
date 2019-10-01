## Description

We have a set of raw data files for our (fictional) e-commerce car shop.

We need to populate our database with the contents of those data files.
We also want to keep track of the result of the import.

## Process

- We have provided some example data files (one for each format we want to cover) in the `./data` folder;
- Data files can be any of these file types: `xml`, `csv` or `json`. In future, new types could be added;
- Data files can be really big. Keep an eye on performance;
- Importer should be started by visiting a URL like `http://localhost?source={data_format}`, where `data_format` can be `xml`, `csv` or `json`;
- Imported product data should be saved to an SQL table named `products`;
- Importer processes should be recorded to an SQL table named `import_logs`;

## Desired SQL structure

#### Table name: `products`

| id | brand  | model    | sku         | price    |
|----|--------|----------|-------------|----------|
| 1  | Nissan | Frontier | 442-77-4953 | 30067.41 |
| 2  | Audi   | A5       | 189-25-4980 | 60897.34 |

#### Table name: `import_logs`

| id | start               | end                 | status     | source |
|----|---------------------|---------------------|------------|--------|
| 1  | 2019-03-23 14:27:51 | 2019-03-23 15:25:03 | Completed  | CSV    |
| 2  | 2019-01-09 12:12:26 | 2019-01-09 12:24:54 | Processing | XML    |
| 3  | 2019-04-13 18:21:11 | 2019-04-13 21:12:43 | Failed     | JSON   |

## Bonus

- We would like to have a REST API implementation to request entries from the `products` table (all products or a single product);
- We would like to have some kind of automated tests for the importer;

## Points to note

- Please fork this Git repository and open a pull request against the original when finished;
- We expect you to spend 4-8 hours on the task;
- We're very much interested in code organisation, DRY and OOP thinking;
