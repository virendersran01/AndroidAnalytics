# AndroidAnalytics

#Download

In your module [![Download](https://api.bintray.com/packages/florent37/maven/AndroidAnalytics/images/download.svg)](https://bintray.com/florent37/maven/AndroidAnalytics/_latestVersion)
```groovy
//not available yet
compile 'com.github.florent37:androidanalytics:1.0.0'
compile 'com.github.florent37:androidanalytics-google:1.0.0'
```

# Register analytics providers

`MainApplication.java`
```java
Analytics.registerProvider(
      new GoogleAnalyticsProvider(this, R.xml.app_tracker)
);
```

# Send events

`MainActivity.java`
```java
Analytics.screen("MainActivity");

button.setOnClickListener(v -> {
         Analytics.event(new AnalyticsEvent()
                 .category("main")
                 .action("click")
                 .label("button")
         );
});
```

# Another analytics provider

```java
Analytics
          .registerProvider(
                  new AnalyticsProvider() {
                      @Override
                      public void event(AnalyticsEvent analyticsEvent) {
                            //send it to your analytics
                      }

                      @Override
                      public void screen(String screenName) {
                            //send it to your analytics
                      }
                  }
          );
```

# Loggin analytics provider

```java
Analytics.registerProvider(
       new AnalyticsLogginProvider("analytics")
);
```

#Credits

Author: Florent Champigny [http://www.florentchampigny.com/](http://www.florentchampigny.com/)

<a href="https://plus.google.com/+florentchampigny">
  <img alt="Follow me on Google+"
       src="https://raw.githubusercontent.com/florent37/DaVinci/master/mobile/src/main/res/drawable-hdpi/gplus.png" />
</a>
<a href="https://twitter.com/florent_champ">
  <img alt="Follow me on Twitter"
       src="https://raw.githubusercontent.com/florent37/DaVinci/master/mobile/src/main/res/drawable-hdpi/twitter.png" />
</a>
<a href="https://www.linkedin.com/in/florentchampigny">
  <img alt="Follow me on LinkedIn"
       src="https://raw.githubusercontent.com/florent37/DaVinci/master/mobile/src/main/res/drawable-hdpi/linkedin.png" />
</a>


License
--------

    Copyright 2016 florent37, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.