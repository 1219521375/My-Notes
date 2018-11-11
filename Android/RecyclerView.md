# RecyclerView 用法总结

1. 为项目添加依赖  
        implementation'com.android.support:recyclerview-v7:26.0'  
2. 在xml文件中添加RecyclerView控件  
        <android.support.v7.widget.RecyclerView  
        android:id="@+id/hot_topic_recycler_view"  
        android:layout_width="match_parent"  
        android:layout_height="match_parent">  
    </android.support.v7.widget.RecyclerView>  
3. 编写itemview的xml页面  
    eg：使用CardView(需要添加依赖)  
4. 创建模型类  
``` public class Event {

    private String depict;

    private String title;

    public Event(String title, String depict) {
        this.depict = depict;
        this.title = title;
    }

    public String getTitle() {
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    public String getDepict() {
        return depict;
    }

    public void setDepict(String depict) {
        this.depict = depict;
    }


}```