# Tips

1.  删除 autopublish 包：
    ``` bash
    $ meteor remove autopublish
    ```

2.  服务器端选择性发布数据给客户端：
    ``` javascript
    Meteor.publish('posts', function() {
        return Posts.find({flagged: false, author: author});
    });
    ```

3.  客户端订阅服务器端发布的数据：
    ``` javascript
    Meteor.subscribe('posts', 'Yoonge');
    ```

4.  客户端选择订阅数据的子集：
    ``` javascript
    Template.posts.helpers({
        posts: function(){
            return Posts.find({author: 'Yoonge', category: 'JavaScript'});
        }
    });
    ```

5.  发布部分字段：
    ``` javascript
    Meteor.publish('posts', function(){
        return Posts.find({}, {
            fields: {
                date: false    // 去掉 date 字段
            }
        });
    });
    ```

6. Meteor 中不能使用传统分页；

7. **To be continued...**
