## 如果参数没有特别说明则是——(类型字符串,长度100)
### 喜酒接口
1. 新增或更新用户信息      
    - API地址     
    ```
    http://student.bluej.cn/index/wedding/upload_user
    ```
    - 参数       
    ```
    wechat_id   （微信id）
    name        （微信昵称）
    province    （省份）
    city        （城市）
    head_img    （头像地址）
    ```
    - 返回结果       
    ```
    code（0为失败,1为成功）
    msg（返回说明）
    wechat_id（微信id）
    ```
2. 新增自己的婚宴      
    - API地址     
    ```
    http://student.bluej.cn/index/wedding/add_wedding
    ```
    - 参数       
    ```
    wechat_id           （微信id）
    wedding_name        （婚宴名称）
    wedding_position    （婚宴地点）
    time                （婚宴时间,注意是时间戳）——（类型字符串,长度11）
    ```     
    - 返回结果       
    ```
    code（0为失败,1为成功,2为已经有属于自己的婚宴）
    msg （返回说明）
    data [wedding_id（自己的婚宴id）,wedding_name（自己的婚宴名字）,wedding_position（自己的婚宴地点）,time（自己的婚宴时间）,sponsor_id（自己的婚宴id）]
    ```
3. 获取婚宴座位      
    - API地址     
    ```
    http://student.bluej.cn/index/wedding/get_wedding
    ```
    - 参数       
    ```
    sponsor_id  （婚宴id）
    ```     
    - 返回结果       
    ```
    wedding_info    [wedding_name（婚宴名字）,wedding_position（婚宴地点）,time（婚宴时间）]
    wedding_seats   [seats（婚宴位置）,name（微信昵称）,head_img（微信头像）]
    ```
4. 参加别人的婚宴      
    - API地址     
    ```
    http://student.bluej.cn/index/wedding/join_wedding
    ```
    - 参数       
    ```
    wechat_id   （微信id）
    sponsor_id  （婚宴id）
    seats       （座位id）——（例如坐在第二张桌第3个位置则是0203）
    time        （婚宴时间,注意是时间戳）——（类型字符串,长度11）
    ```     
    - 返回结果       
    ```
    code（0为失败,1为成功,2为同一时间已参加别人的婚宴,3位置已被别人选择,要新页面）
    msg（返回说明）
    data [wedding_name（参与的婚宴名字）,wedding_position（参与的婚宴地点）,time（参与的婚宴时间）]
    ```
5. 改变自己的座位     
    - API地址     
    ```
    http://student.bluej.cn/index/wedding/change_seats
    ```
    - 参数       
    ```
    wechat_id   （微信id）
    sponsor_id  （婚宴id）
    seats       （座位id）——（例如坐在第二张桌第3个位置则是0203）
    ```     
    - 返回结果       
    ```
    code（0为失败,1为成功,2位置已被别人选择,要新页面）
    msg（返回说明）
    ```
6. 添加六个位置   
    - API地址     
    ```
    http://student.bluej.cn/index/wedding/add_seats
    ```
    - 参数       
    ```
    sponsor_id  （婚宴id）
    ```     
    - 返回结果       
    ```
    code（0为失败,1为成功,2还有空白座位,要新页面）
    msg（返回说明）
    ```  