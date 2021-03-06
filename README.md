# About
管理android view的选中状态

# Gradle
[![](https://jitpack.io/v/zj565061763/selection.svg)](https://jitpack.io/#zj565061763/selection)

# 简单demo
![](https://github.com/zj565061763/selection/blob/master/screenshot/selection.gif?raw=true)

```java
public class MainActivity extends AppCompatActivity
{
    private TextView mTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mTextView = findViewById(R.id.textview);

        mTextView.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View v)
            {
                // 切换选中状态
                mTextView.setSelected(!mTextView.isSelected());
            }
        });

        FViewSelection.ofTextView(mTextView).setConfig(new PropertiesConfig<TextViewProperties>()
        {
            @Override
            public void config(TextViewProperties normal, TextViewProperties selected)
            {
                // 配置正常状态的参数
                normal.setTextColor(Color.BLUE).setTextSize(60);

                // 配置选中状态的参数
                selected.setTextColor(Color.RED).setTextSize(100);
            }
        }).setSelected(false);
    }
}
```

# 目前支持的配置
* textColor
TextView字体颜色

* textSize  
TextView字体大小

* imageResId
ImageView资源图片

* background
View的背景

* alpha    
View的透明度

* width    
View的宽度

* height    
View的高度

* visibility
View的可见状态