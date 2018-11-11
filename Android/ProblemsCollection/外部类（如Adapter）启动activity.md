## 在外部类中 
* 写在外部的adapter viewHolder中调用intent跳转activity时  
* 嵌套的fragment中跳转activity

```
Intent intent = new Intent(getActivity(),targetActivity.class);
```
报错无法使用，无法通过getActivity()获取context

## 解决方法
* 定义自己的MyApplication类替换系统生成的Application
```
public class MyApplication extends Application {
    private static Context sContext;
    
    @Override
    public void onCreate() {
        super.onCreate();
        sContext = getApplicationContext();
    }

    public static Context getContext() {
        return sContext;
    }
}
```
* 同时必须在AndroidManifest.xml中配置以下内容
```
<application
        android:name="包名.MyApplication"
        ...>
        ...
    </application>
```
之后直接调用静态getContext()方法即可获取context实例  
例如：
```
public void onClick(View v) {
         Intent intent = new Intent(v.getContext(), EventActivity.class);
         v.getContext().startActivity(intent);
}
```

