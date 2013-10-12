---
layout : post
title : Sms Conversations
---

从源码分析读取短信分组的方法。
源码的`android.provider.Telephony`类包含了有关短信操作的内容。

这个类中有这么一个类
<code>
public static final class Conversations
        implements BaseColumns, TextBasedSmsColumns {
    /**
     * The content:// style URL for this table
     */
    public static final Uri CONTENT_URI =
        Uri.parse("content://sms/conversations");

    /**
     * The default sort order for this table
     */
    public static final String DEFAULT_SORT_ORDER = "date DESC";

    /**
     * The first 45 characters of the body of the message
     * <P>Type: TEXT</P>
     */
    public static final String SNIPPET = "snippet";

    /**
     * The number of messages in the conversation
     * <P>Type: INTEGER</P>
     */
    public static final String MESSAGE_COUNT = "msg_count";
}
</code>
