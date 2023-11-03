# 实现 Oracle-MySQL 的表对比
## 对比表结构
### 字段属性
在 Oracle 的 `ALL_TAB_COLUMNS` 和 MySQL 的 `INFORMATION_SCHEMA.COLUMNS` 之间，以下字段是既重要又可对比的：
1. **表名和列名**:

- Oracle: `TABLE_NAME`, `COLUMN_NAME`

- MySQL: `TABLE_NAME`, `COLUMN_NAME`

这些字段是基础的，用于确定我们正在比较的是哪个表和列。

2. **数据类型**:

- Oracle: `DATA_TYPE`

- MySQL: `DATA_TYPE`, `COLUMN_TYPE`

数据类型是描述列可以存储什么类型数据的关键属性。

3. **是否可为空**:

- Oracle: `NULLABLE`

- MySQL: `IS_NULLABLE`

这决定了列是否可以包含空值。

4. **默认值**:

- Oracle: `DATA_DEFAULT`

- MySQL: `COLUMN_DEFAULT`

如果某列有默认值，插入时可以不指定该列的值。

5. **数据精度和刻度**:

- Oracle: `DATA_PRECISION`, `DATA_SCALE`

- MySQL: `NUMERIC_PRECISION`, `NUMERIC_SCALE`

对于数字类型的列，这些值描述了数字的大小和小数点后的位数。

6. **字符集和排序规则**:

- Oracle: `CHARACTER_SET_NAME`

- MySQL: `CHARACTER_SET_NAME`, `COLLATION_NAME`

对于文本类型的数据，字符集和排序规则决定了如何存储和比较数据。

7. **权限**:

- MySQL: `PRIVILEGES`

与权限有关的字段在 MySQL 中可用，描述了对该列的操作权限。


## 对比数据
