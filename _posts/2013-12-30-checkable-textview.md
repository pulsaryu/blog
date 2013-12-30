---
layout: post
title: 创建CheckedTextView
category: blog
---

自定义创建CheckedTextView, 实现checkable, 并增加 OnCheckedChangeListener (这个源代码的CheckedTextView可以是没有的).

首先是实现 Checkable, 这个比较简单.
{% highlight java %}
public class CheckedTextView extends TextView implements Checkable {

    private boolean mIsChecked;

    public CheckedTextView(Context context) {
        this(context, null);
    }

    public CheckedTextView(Context context, AttributeSet attrs) {
        this(context, attrs, 0);
    }

    public CheckedTextView(Context context, AttributeSet attrs, int defStyle) {
        super(context, attrs, defStyle);
    }

    @Override
    public void setChecked(boolean checked) {
        mIsChecked = checked;
    }

    @Override
    public boolean isChecked() {
        return mIsChecked;
    }

    @Override
    public void toggle() {
        setChecked(!mIsChecked);
    }
}
{% endhighlight %}
