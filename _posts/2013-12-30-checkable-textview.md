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

创建 OnCheckedChangeListener 接口
{% highlight java %}
public static interface OnCheckedChangeListener {
    public void onCheckedChanged(CheckedTextView view, boolean checked);
}
{% endhighlight %}
实现 OnCheckedChangeListener 接口
{% highlight java %}
private OnCheckedChangeListener mOnCheckedChangeListener;

@Override
public void setChecked(boolean checked) {
    if (mIsChecked != checked) {
        mIsChecked = checked;
        if (mOnCheckedChangeListener != null) {
            mOnCheckedChangeListener.onCheckedChanged(this, checked);
        }
    }
}

public void setOnCheckedChangeListener (OnCheckedChangeListener listener) {
    mOnCheckedChangeListener = listener;
}
{% endhighlight %}
