# scalastyle_config

The [Scalastyle](http://www.scalastyle.org/sbt.html) configuration we use for our in-house Scala projects.

# Using with the Scalastyle SBT plugin

Assuming your project already has the [plugin](http://www.scalastyle.org/sbt.html) setup, update your `build.sbt` to include the following settings:

```scala
scalastyleConfigUrl := Some("https://raw.githubusercontent.com/zendesk/scalastyle_config/master/scalastyle-config.xml"),
scalastyleConfigUrlCacheFile := "scalastyle-config.xml",
scalastyleConfigRefreshHours := 168 // Weekly instead of daily.
```

NOTE: if you're using a recent version of Zendesk's (internal) `zendesk_sbt_base_settings` plugin, then these settings are already setup for you.

The `scalastyleConfigUrlCacheFile` setting puts the downloaded file into the root of your repository, which is where IntelliJ expects it to be.

To ensure that the download config is *not* part of your Git repository, add a line containing `scalastyle-config.xml` to `.gitignore` (which can be in the root of your repository, or the global one).
