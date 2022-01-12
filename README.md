# hbase_learning
hbase 学习

### hbase shell 语句
1. hbase 查询结果显示中文
    - HBase 查询出来的数据，中文显示为十六进制乱码
    - `get 'namespacedemo:tabledemo','1111',{FORMATTER => 'toString' }`
2. HBase统计数据量
    - HBase 统计数据量速率过慢
    - `count 'namespacedemo:tabledemo', INTERVAL => 10000, CACHE => 10000`
3. HBase 通过字段内同过滤数据并统计
    - HBase 通过指定字段内同过滤数据，并进行统计
    - `scan 'namespacedemo:tabledemo',{FILTER=>"SingleColumnValueFilter('info','pubtime',=,'regexstring:2021-12-11')"}`
4. HBase 根据列名过滤数据
    - 查询结果只取某一列数据
    - `scan 'scores',{COLUMNS=>'course:art'}`
5. HBase 限制条数查询
    - `scan 'scores',{LIMIT => 10}`