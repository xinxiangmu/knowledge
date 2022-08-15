# mysql
## 主要命令行
- select version();	 查看服务器版本 5.7版本支持json
- 
- mysql -uroot -p 密码登陆服务器
- mysql json 使用语法 https://www.cnblogs.com/xxhxs-21/p/15897248.html
 - https://www.cnblogs.com/inkyi/p/15745242.html
 
- json 需要虚拟索引，提升性能
https://www.csdn.net/tags/OtTaEgysODQzMS1ibG9n.html
- 注解的代码需要注意，因为有些可能会在真正的代码执行之前做验证，这个就是注解内部给做的操作，所以需要注意，如果有全局异常处理的类，会出现这个问题

- Type handler was null on parameter mapping for property 'fSceneInfo'. It was either not specified and/or could not be found for the javaType (java.util.List) : jdbcType (VARCHAR) combination.
mybaits 对象需要执行type处理器，所有使用此字段key的地方都需要配置，配置不同的地方格式不一样，需要注意细节
- xml中是这样的，    <result column="f_scene_info" jdbcType="VARCHAR"  property="fSceneInfo"  typeHandler="com.huobi.global.util.MySqlJsonHandler"  />
- 其他的是这样的，需要注意细节f_scene_info = #{fSceneInfo,jdbcType=VARCHAR,typeHandler=com.huobi.global.util.MySqlJsonHandler}

@MappedJdbcTypes({JdbcType.VARCHAR})
@Slf4j
@Component
@MappedTypes({List.class, IntelligentWorkOrderConfigExample.class})
public class MySqlJsonHandler<T extends Object> extends BaseTypeHandler<T> {


    private Class<T> clazz;
    @Override
    public void setNonNullParameter(PreparedStatement preparedStatement, int i, T t, JdbcType jdbcType) throws SQLException {

        preparedStatement.setString(i,JSONObject.toJSONString(t));
    }

    @Override
    public T getNullableResult(ResultSet resultSet, String s) throws SQLException {
        return JSONObject.parseObject(resultSet.getString(s),clazz);
    }

    @Override
    public T getNullableResult(ResultSet resultSet, int i) throws SQLException {
        return JSONObject.parseObject(resultSet.getString(i),clazz);
    }

    @Override
    public T getNullableResult(CallableStatement callableStatement, int i) throws SQLException {
        return JSONObject.parseObject(callableStatement.getString(i),clazz);
    }
}
