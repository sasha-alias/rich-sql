# Rich SQL

Rich SQL - data visualisation extension for SQL

This is the short specification of `Rich SQL` language extension implemnted by [SQL Tabs](http://www.sqltabs.com/).

Estension of SQL scripts for declaring the way obtained results have to be presented.

SQL script can be split to blocks by a comment line started with 3 dashes: `---`

Each block can be annotated with a preffered way of representation:

``` sql
--- <annotation> <options>
```

Annotations:

### table

``` sql
--- table
```

Represent a result as a standard table

### crosstable

``` sql
--- crosstable
```

Represent a result as a crosstable.
By default the first column is taken as a vertical axis, the second columns as horizontal axis, the rest of the columns as cross table values.

### chart

``` sql
--- chart <chart_type> <options>
```

Represent a result as a chart of a `chart_type`.

Chart types:

    - area
    - area-spline
    - area-step
    - bar
    - donut
    - line
    - pie
    - spline
    - step

### hidden

``` sql
--- hidden
```

Do not represent a result at all.

### id

``` sql
--- id
```

ID of a script. Should be defined once per script.
Serves for storing results in a further systems.
ID supposed to uniquely identify a file/document in a system.

### every

``` sql
--- every <options>
```

If a script supposed to be run regulary defines a schedule of execution. (a la cron)
The specification of a schedule to be defined.

### map

``` sql
--- map <options>
```

Represent result on a geographical map.
Options to be defined.

### markdown blocks

``` sql
/** <markdown> **/
```

Text within `/** **/` block is interpreted as a static markdown markup to be displayed together with a result.

