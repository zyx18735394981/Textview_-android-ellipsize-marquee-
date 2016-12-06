# Textview_-android-ellipsize-marquee-
textview的跑马灯效果
 <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/hello"
        android:singleLine="true"     //只有单行才可能有跑马灯效果
        android:ellipsize="marquee"    //跑马灯效果
        android:marqueeRepeatLimit="marquee_forever"   //跑马灯重复次数        
        android:focusable="true" //由于Activity中没有写任何方法，故此处让其获得焦点
        android:focusableInTouchMode="true"/>
        
        
        
        android:ellipsize="start"        省略号在开头        
        android:ellipsize="middle"       省略号在中间        
        android:ellipsize="end"          省略号在结尾        
        android:ellipsize="marquee"      跑马灯显示
