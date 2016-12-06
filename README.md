# Textview_-android-ellipsize-marquee-
textview的跑马灯效果

                 <com.zyx.paomadeng_textview_12_6.View.MarqueeTextView
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

需要自定义控件
  
                          package com.zyx.paomadeng_textview_12_6.View;
                            import android.content.Context;
                            import android.graphics.Rect;
                            import android.text.TextUtils.TruncateAt;
                            import android.util.AttributeSet;
                             import android.widget.TextView;

                              /**
                               *
                                * 一直走马灯效果控件 
                                * @author zuolongsnail
                                */
                            public class MarqueeTextView extends TextView {

                                    public MarqueeTextView(Context context) {
                                            super(context);
                                            createView();
                                     }

                                      public MarqueeTextView(Context context, AttributeSet attrs) {
                                              super(context, attrs);
                                              createView();
                                       }

                                       public MarqueeTextView(Context context, AttributeSet attrs, int defStyle) {
                                                 super(context, attrs, defStyle);
                                                createView();
                                      }

                                          private void createView() {
                                                   setEllipsize(TruncateAt.MARQUEE);
                                                    setMarqueeRepeatLimit(-1);
                                                    setFocusableInTouchMode(true);
                                         }

                                          @Override
                                          protected void onFocusChanged(boolean focused, int direction,
                                                                                Rect previouslyFocusedRect) {
                                            if (focused) {
                                                  super.onFocusChanged(focused, direction, previouslyFocusedRect);
                                                }
                                            }

                                        @Override
                                             public void onWindowFocusChanged(boolean focused) {
                                                      if (focused) {
                                                     super.onWindowFocusChanged(focused);
                                               }
                                                  }
                                                  @Override
                                                  public boolean isFocused() {
                                                      return true;
                                                  }

                                              }  
