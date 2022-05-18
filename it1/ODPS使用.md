# sql语法
- with tmp as（select* from txx） cte用户
- if(GROUPING(xx)==0,xx ,'ALL')AS xx group聚合条件判断
- CONCAT(1,'-',2) 列合并
- select a.`(ds|buyer_id|div_pay_amt)?+.+` select 排除以下的列
- WM_CONCAT(',', image_url)  行转列
- ALTER TABLE xx ADD PARTITION (ds='${bizdate}.xx'); 增加新的分区
- left semi join  白名单
- left anti join 黑明单

# 参数
- SET odps.sql.joiner.instances =5000; 设置join的数量
- SET odps.sql.reducer.instances =5000; 设置reduce的数量
- set odps.sql.mapjoin.memory.max=2048 设置mapjoin内存大小
- alter table my_log partition(ds='20140101') archive; 压缩表
- set odps.instance.priority=0 设置执行优先级
- percentile_approx 大数据量百分位统计
- purge all; 清除缓存
- -- SET odps.sql.mapper.split.size=3000; mapper的处理大小
