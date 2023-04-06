# day15 posa_bottom_bar



A vertical fullscreen scroll implementation that snaps in place, similar to the TikTok app.

# 1-Add the  posa_bottom_bar dependency in your pubspec.yaml file.

```
dependencies:
  posa_bottom_bar: ^latest_version
```

# 2-Import the   posa_bottom_bar  package in your dart file.

```
import 'package:persistent_bottom_nav_bar/persistent_tab_view.dart';

```


# 4-use him like this

```
@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("POSA BOTTOM BAR"),
        centerTitle: true,
      ),
      body: PosaBottomBar(
        // CHILD IS REQUIRED
        child: pages
            .elementAt(currentIndex), // ADD HERE YOUR PAGE OR PAGES NAVIGATOR
        // ICONS IS REQUIRED
        icons: const [
          Ionicons.home_outline,
          Ionicons.settings_outline,
          Ionicons.bookmark_outline,
          Ionicons.person_outline,
        ],
        // ONCHANGE IS REQUIRED
        onChanged: (i) {
          setState(() {
            debugPrint("TAP $i");
            currentIndex = i;
          });
        },
        // ON LONG PRESS FNC
        onLongPress: (i) {
          setState(() {
            debugPrint("LONG PRESS $i");
          });
        },
        alignment: Alignment.bottomCenter,
        // ------ height and margin for bottom bar ----- //
        height: 0.16,
        margin: 0.05,
        // ------  ----- //

        // ------ Elevation & Color for bottom bar ----- //
        elevation: 10,
        shadowColor: Colors.black,
        // ------  ----- //

        borderRadius: 35, // RADUIS (FOR BOTTOM BAR)
        backgroundColor: Colors.blueAccent, // BACKGROUND COLORS (FOR BOTTOM BAR)
        dotColor: Colors.white, // COLORS OF DOT
        iconColor: Colors.white, // COLORS OF ICON
        dotSize: 5.0, iconSize: 24.0, // SIZE OF DOT AND ICONS

        // ------ Animation elevation and opacity ----- //
        isElevationAnimation: false,
        elevationAnimationOpacity: 0.3,
        elevationAnimationDuration: const Duration(milliseconds: 1500),
        // ------  ----- //

        // ------ Animation Icons ------ //
        isAnimatedIcon: false,
        // ------  ------ //
      ),
    );
  }
```








