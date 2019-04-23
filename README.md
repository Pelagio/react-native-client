
launchdarkly-react-native-client
================================

Getting started
---------------

`$ npm install launchdarkly-react-native-client --save`

Mostly automatic installation
-----------------------------

`$ react-native link launchdarkly-react-native-client`

Usage
-----

```javascript
import LDClient from 'launchdarkly-react-native-client';

async componentDidMount() {
    try {
      let client = new LDClient();

      let clientConfig =
          { "mobileKey": "YOUR_MOBILE_KEY",
            "stream": true,
            "offline": false
          };

      let userConfig = { "key": "user_key" };

      await client.configure(clientConfig, userConfig);
      this.setState({ldClient: client});
      let res = await this.state.ldClient.stringVariation("MY_STRING_FLAG_KEY", "");
      Alert.alert('LD Server Response', String(res));
    } catch(err) {
      console.error(err);
    }
}
```

Learn more
-----------

Check out our [documentation](http://docs.launchdarkly.com) for in-depth instructions on configuring and using LaunchDarkly. You can also head straight to the [complete reference guide for this SDK](http://docs.launchdarkly.com/docs/react-native-sdk-reference).

Testing
-------

We run integration tests for all our SDKs using a centralized test harness. This approach gives us the ability to test for consistency across SDKs, as well as test networking behavior in a long-running application. These tests cover each method in the SDK, and verify that event sending, flag evaluation, stream reconnection, and other aspects of the SDK all behave correctly.

Contributing
------------

We encourage pull-requests and other contributions from the community. We've also published an [SDK contributor's guide](http://docs.launchdarkly.com/docs/sdk-contributors-guide) that provides a detailed explanation of how our SDKs work.

About LaunchDarkly
-----------

* LaunchDarkly is a continuous delivery platform that provides feature flags as a service and allows developers to iterate quickly and safely. We allow you to easily flag your features and manage them from the LaunchDarkly dashboard.  With LaunchDarkly, you can:
    * Roll out a new feature to a subset of your users (like a group of users who opt-in to a beta tester group), gathering feedback and bug reports from real-world use cases.
    * Gradually roll out a feature to an increasing percentage of users, and track the effect that the feature has on key metrics (for instance, how likely is a user to complete a purchase if they have feature A versus feature B?).
    * Turn off a feature that you realize is causing performance problems in production, without needing to re-deploy, or even restart the application with a changed configuration file.
    * Grant access to certain features based on user attributes, like payment plan (eg: users on the ‘gold’ plan get access to more features than users in the ‘silver’ plan). Disable parts of your application to facilitate maintenance, without taking everything offline.
* LaunchDarkly provides feature flag SDKs for
    * [Java](http://docs.launchdarkly.com/docs/java-sdk-reference "Java SDK")
    * [JavaScript](http://docs.launchdarkly.com/docs/js-sdk-reference "LaunchDarkly JavaScript SDK")
    * [PHP](http://docs.launchdarkly.com/docs/php-sdk-reference "LaunchDarkly PHP SDK")
    * [Python](http://docs.launchdarkly.com/docs/python-sdk-reference "LaunchDarkly Python SDK")
    * [Go](http://docs.launchdarkly.com/docs/go-sdk-reference "LaunchDarkly Go SDK")
    * [Node.JS](http://docs.launchdarkly.com/docs/node-sdk-reference "LaunchDarkly Node SDK")
    * [Electron](http://docs.launchdarkly.com/docs/electron-sdk-reference "LaunchDarkly Electron SDK")
    * [.NET](http://docs.launchdarkly.com/docs/dotnet-sdk-reference "LaunchDarkly .Net SDK")
    * [Ruby](http://docs.launchdarkly.com/docs/ruby-sdk-reference "LaunchDarkly Ruby SDK")
    * [iOS](http://docs.launchdarkly.com/docs/ios-sdk-reference "LaunchDarkly iOS SDK")
    * [Android](http://docs.launchdarkly.com/docs/android-sdk-reference "LaunchDarkly Android SDK")
* Explore LaunchDarkly
    * [launchdarkly.com](http://www.launchdarkly.com/ "LaunchDarkly Main Website") for more information
    * [docs.launchdarkly.com](http://docs.launchdarkly.com/  "LaunchDarkly Documentation") for our documentation and SDKs
    * [apidocs.launchdarkly.com](http://apidocs.launchdarkly.com/  "LaunchDarkly API Documentation") for our API documentation
    * [blog.launchdarkly.com](http://blog.launchdarkly.com/  "LaunchDarkly Blog Documentation") for the latest product updates
    * [Feature Flagging Guide](https://github.com/launchdarkly/featureflags/  "Feature Flagging Guide") for best practices and strategies