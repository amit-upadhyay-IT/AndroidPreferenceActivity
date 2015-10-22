# AndroidPreferenceActivity - RELEASE NOTES

## Version 3.0.0 (Oct. 21th 2015)

A major release, which introduces the following changes:

- The project has been migrated from the legacy Eclipse ADT folder structure to Android Studio. It now uses the Gradle build system and the library as well as the example app are contained by one single project.
- The library can now be added to Android apps using the Gradle dependency `com.github.michael-rapp:android-preference-activity:3.0.0` (https://github.com/michael-rapp/AndroidPreferenceActivity/issues/7)

## Version 2.2.1 (Sept. 10th 2015)

A bugfix release, which fixes the following issue:

- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/10

## Version 2.2.0 (June 3rd 2015)

A feature release, which introduces the following changes:

- The signatures of the methods of the class `WizardListener` have been changed. Instances of the class `Bundle` are now only used as return values, when the activity is not about to be closed. Additionally, `Bundle` instances, which contain the arguments of the currently shown fragment, are now passed to each method as a parameter.

## Version 2.1.1 (June 1st 2015)

A minor release, which provides the following changes:

- It is now possible to add listeners to the class `PreferenceActivity`, which are notified, when the currently shown preference fragment changes.

## Version 2.1.0 (May 31th 2015)

A feature release, which introduces the following changes:

- It is now possible to pass parameters within a `Bundle` from one fragment of a wizard to an other. Therefore the method signatures of the interface `WizardListener` have been changed.
- Fragment transitions are now properly handled, when multiple instances of the same class are used as the preference headers' fragments.
- Added the layout `R.layout.preference_child`, which can be used as as preference's layout, if a left indent should be added. May be useful for creating hierarchical preference screens together with the `android.dependency` attribute.
- Added a `FrameLayout` to the `PreferenceActivity`. It can be accessed by using the ID `R.id.preference_activity_frame_layout`. Additionally, `getFrameLayout`-methods have been added to allow referencing a `PreferenceActivity`'s, respectively a `PreferenceFragment`'s, frame layout.
- The issue https://github.com/michael-rapp/AndroidPreferenceActivity/issues/9 has been solved. The library now relies on the AppCompat v7 revision 22 support library. Revision 21 is not supported anymore.

## Version 2.0.8 (Apr. 19th 2015)

A bugfix release, which fixes the following issues:

- The `FrameLayout` of a `PreferenceFragment` can now be accessed using the ID `R.id.preference_fragment_frame_layout`.
- API level 22 is now used.

## Version 2.0.7 (Feb. 7th 2015)

A bugfix release, which fixes the following issues:

- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/8

## Version 2.0.6 (Nov. 16th 2014)

A bugfix release, which fixes the following issues:

- Changed the appearance of the dialog's buttons to be identically on Lollipop-devices, as well as on pre-Lollipop devices.

## Version 2.0.5 (Nov. 12th 2014)

A bugfix release, which fixes the following issues:

- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/6

## Version 2.0.4 (Nov. 11th 2014)

A minor release, which provides the following changes:

- The texts of buttons are not bold anymore.

## Version 2.0.3 (Nov. 5th 2014)

A minor release, which provides the following changes:

- Added a dimen resource, which specifies the height of the large toolbar.
- Added the possibility to register a listener, which is notified about a `HideViewOnScrollAnimation`'s internal state.

## Version 2.0.2 (Nov. 5th 2014)

A minor release, which provides the following changes:

- The minimum height and the vertical padding of a preference have been changed.

## Version 2.0.1 (Nov. 5th 2014)

A bugfix release, which fixes the following issues:

- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/4
- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/5

## Version 2.0.0 (Nov. 4th 2014)

A major release, which introduces the following features:

- The UI has been re-designed according to the Android 5 "Material Design" guidelines. To provide Material Design even on pre-Lollipop devices (API level less than 21), the AppCompat v7 revision 21 support library is used.
- The methods to set/retrieve shadow widths and colors have been replaced by according methods, which allow to set/retrieve elevations like used by the Android SDK 21.
- Added style attributes, which allow easier customizing of a `PreferenceFragment`'s appearance from within a theme.
- The button bar, which contains the button, which allows to restore the default values of a `PreferenceFragment`'s preferences, is now animated to become hidden when the user scrolls downwards and to become shown when the user scrolls upwards.

## Version 1.2.1 (Oct. 25th 2014)

A bugfix release, which fixes the following issues:

- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/2
- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/3

## Version 1.2.0 (Oct. 25th 2014)

A feature release, which introduces the following functionalities:

- The interface `RestoreDefaultsListener` does now provide an additional method, which allows to determine whether a single preference's default value should be restored, or not. This functionality replaces the methods to manage a black list and to specify, whether disabled preferences should be restored, which have been offered previously by the class `PreferenceFragment`.
- Added a method to the interface `RestoreDefaultsListener`, which is invoked, when a preference's default value has been restored.

## Version 1.1.2 (Oct. 24th 2014)

A bugfix release, which fixes the following issue:

- https://github.com/michael-rapp/AndroidPreferenceActivity/issues/1

## Version 1.1.1 (Oct. 24th 2014)

A minor release, which provides the following changes:

- Added a black list to the class `PreferenceFragment`, which allows to specify the keys of the preferences, whose default values should not be restored.

## Version 1.1.0 (Oct. 23th 2014)

A feature release, which introduces the following functionalities:

- The library does now provide a class, which is extended from the Android SDK's built-in `PreferenceFragment`. This class allows to show a button, which may be used to restore the default values of the fragment's preferences.

## Version 1.0.1 (Oct. 21th 2014)

A minor release, which provides the following changes:

- Added a public inner class, which implements the interface `android.os.parcelable.Creator` to the class `PreferenceHeader` in order to allow creating instances from a `Parcel`.
- Prepared for Android 5.0 (API level 21).

## Version 1.0.0 (Oct. 19th 2014)

The first stable release, which provides an activity, an alternative implementation of the Android SDK's built-in `PreferenceActivity`. The implementation initially provides the following features:
	
- The activity's navigation allows to show preference headers, which categorize the preferences of a `PreferenceFragment`. Furthermore, regular Fragments can be shown. Besides a title, the preference headers may contain an icon and a summary and it is possible to launch an intent when a header is selected.
- The activity's preference headers can be defined via XML resources, which are compatible to the ones used to initialize the Android SDK's built-in `PreferenceActivity`. Alternatively, the preference headers can be added or removed dynamically at runtime, which causes the current selected preference header to be adapted automatically.
- The activity provides methods, which easily allow to access its child views in order to manipulate their appearance. For the most common manipulations even dedicated methods are provided.
- The library allows to override the behavior of the action bar's back button in order to use it for navigating on devices with a small screen.
- It is possible to launch the activity using an intent, which specifies the preference header, which should be initially selected. Such an intent also allows to hide the navigation.
- By specifying appropriate intent extras, it is also possible to use the activity as a wizard, which provides an alternative navigation, which allows to navigate from one step of the wizard to an other. The navigation can be observed and influenced by implementing and registering an appropriate listener.
- The activity is visually-consistent with Android's built-in `PreferenceActivity`.