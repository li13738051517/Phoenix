# Pull-to-Refresh.Rentals-Android

This project aims to provide a simple and customizable pull to refresh implementation.

<img src="https://d13yacurqjgara.cloudfront.net/users/125056/screenshots/1650317/realestate-pull_1-2-3.gif" alt="alt text" style="width:200;height:200">

Check this [project on dribble] (https://dribbble.com/shots/1650317-Pull-to-Refresh-Rentals)

[Hire us!] (http://yalantis.com/)


#Usage

*For a working implementation, Have a look at the Sample Project - sample*

1. Include the library as local library project.
2. Include the PullToRefreshView widget in your layout.

	```xml
    <com.yalantis.pulltorefresh.library.PullToRefreshView
        android:id="@+id/pull_to_refresh"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <ListView
            android:id="@+id/list_view"
            android:divider="@null"
            android:dividerHeight="0dp"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

    </com.yalantis.pulltorefresh.library.PullToRefreshView>
    ```

3. In your `onCreate` method refer to the View and setup OnRefreshListener.
	```java
    mPullToRefreshView = (PullToRefreshView) findViewById(R.id.pull_to_refresh);
    mPullToRefreshView.setOnRefreshListener(new PullToRefreshView.OnRefreshListener() {
        @Override
        public void onRefresh() {
            mPullToRefreshView.postDelayed(new Runnable() {
                @Override
                public void run() {
                    mPullToRefreshView.setRefreshing(false);
                }
            }, REFRESH_DELAY);
        }
     });
     ```

#Customization

There is one attribute which applicable to `PullToRefreshView`.

   * `type` type of refresh animation
   * You can also set this attribute from your java code by calling `setRefreshStyle(int type)`

To customize drawables you can change:
   * sun.png - Sun image
   * sky.png - background image
   * buildings.png - foreground image

# Misc
If you need to change progress state: 
```java
	mPullToRefreshView.setRefreshing(boolean isRefreshing)
```
#Compatibility
  
  * Android Gelly Bean 4.1+
  
# Changelog

### Version: 1.0

  * Initial Build
  
## License

    Copyright 2015, Yalantis

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.