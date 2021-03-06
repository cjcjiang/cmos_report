# MyBatis Learning

## Chapter2
### 20180515
1. java中的byte[]对应数据库中的BLOB,LONGVARBINARY与二进制流有关的字段类型。
2. Domain Object中不应使用基本类型。应使用Integer等。基本类型总会有默认值。但数据库里可能可以是null，就会有问题。
3. 当所有的mapper都有对用的接口的情况下，可以直接扫描接口所在包，自动注册mapper.xml。
![mappers配置](https://ws1.sinaimg.cn/large/e2989da6ly1frbupwbt0xj20fy032aae.jpg)
4. resultMap标签用于配置java对象的属性和查询结果列的对应关系。
5. 当返回值为多个时，接口中方法的返回值直接是list就行。mapper.xml中的resultType就是Domain Object的type。当属性名称不一样时，要在sql中设置别名。
![多返回值](https://ws1.sinaimg.cn/large/e2989da6ly1frbvdkqjsxj20ns08y40h.jpg)
6. sql返回的结果包含多张表的信息。
    - 直接在一个DO中添加其它DO的属性。
    ![类拓展](https://ws1.sinaimg.cn/large/e2989da6ly1frc02l9fzhj20g3085400.jpg)
    - 在一个DO中直接将其它DO作为属性添加。
    ![加对象](https://ws1.sinaimg.cn/large/e2989da6ly1frc03jfbg6j208i05gglw.jpg)
    ![加对象sql](https://ws1.sinaimg.cn/large/e2989da6ly1frc03ytqt9j20p00axgo7.jpg)
7. 使用insert时，特殊数据类型，如blob，datetime，为防止类型错误，应指定jdbcType值。
8. 当主键自增时，insert后返回主键值。
    - 使用userGeneratedKeys获得主键。
    ![gkey](https://ws1.sinaimg.cn/large/e2989da6ly1frc3opwww9j20li087ac6.jpg)
    - 使用selectKey获得主键。
    ![skey-mysql](https://ws1.sinaimg.cn/large/e2989da6ly1frc3qn7kpzj20p70atdj2.jpg)
    ![skey-oracle1](https://ws1.sinaimg.cn/large/e2989da6ly1frc3qzajcej20p608740q.jpg)
    ![skey-oracle2](https://ws1.sinaimg.cn/large/e2989da6ly1frc3rdn7ooj20oy01yt91.jpg)
9. 当接口方法中，需要传入多个参数时，使用@Param注解。
    - 当只有一个入参时，MyBatis不关心这个参数叫什么名字就会直接把这个唯一的参数值拿来用。
    - 多个参数为非Object类型。
    ![非obj](https://ws1.sinaimg.cn/large/e2989da6ly1frc4rlpb3bj20g202kq3g.jpg)
    - 多个参数为Object类型。在sql语句中需要点取值。如：#{user.id}，#{role.enabled}。
    ![obj参数](https://ws1.sinaimg.cn/large/e2989da6ly1frcz6wwpjnj20du02l74p.jpg)

### 20180516
10. 需要学习反射来理解mybatis的接口动态代理的原理。





