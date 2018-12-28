错误代码： 1293
Incorrect table definition; there can be only one TIMESTAMP column with CURRENT_TIMESTAMP in DEFAULT or ON UPDATE clause

表中出现多个timestamp并设置为current_timestamp的时候报错

原因是当你给一个timestamp设置为on updatecurrent_timestamp的时候，其他的timestamp字段需要显式设定default值

但是如果你有两个timestamp字段，但是只把第一个设定为current_timestamp而第二个没有设定默认值，MySQL能成功建表,但是反过来就不行...