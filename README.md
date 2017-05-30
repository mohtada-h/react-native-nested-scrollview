# react-native-nested-scrollview
React native wrapper for android NestedScrollView.
It's extract from [react-native-bottom-sheet-behavior](https://github.com/cesardeazevedo/react-native-bottom-sheet-behavior)

## Install

`$ npm install react-native-nested-scrollview`

### Install with RNPM

`$ react-native link react-native-nested-scrollview`

### Install Manually

Edit the current files as follows.

MainApplication.java

```diff

+   import com.mohtada.nestedscrollview.NestedScrollViewPackage;

    public class MainApplication extends Application implements ReactApplication {

      @Override
      protected List<ReactPackage> getPackages() {
        return Arrays.<ReactPackage>asList(
            new MainReactPackage(),
+           new NestedScrollViewPackage()
        );
      }
    }

```

android/app/build.gradle


```diff

    dependencies {
        compile fileTree(dir: "libs", include: ["*.jar"])
        compile "com.android.support:appcompat-v7:23.0.1"
        compile "com.facebook.react:react-native:+"  // From node_modules
+       compile project(':react-native-nested-scrollview')
    }

```

android/settings.gradle

```diff

include ':app'

+   include ':react-native-nested-scrollview'
+   project(':react-native-nested-scrollview').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-nested-scrollview/android')

```

## Usage

You should use `NestedScrollView` instead of `ScrollView`.

```js

    import NestedScrollView from 'react-native-nested-scrollview';

```

```jsx

    render() {
      return (
          <NestedScrollView>
            <NestedScrollView>
            </NestedScrollView>
          </NestedScrollView>
      );
    }

```