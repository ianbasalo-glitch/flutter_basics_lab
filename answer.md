GITHUB REPOSITORY LINK: 
https://github.com/ianbasalo-glitch/flutter_basics_lab.git

activity2


Experiment: inside _addGlass, move _glasses++ outside of setState and tap +. Write down what
happens in your answers file, then put it back.
Answer: After moving _glasses++ outside setState() and pressing the plus button, the displayed water count did not refresh as expected. Flutter was not informed that the state had changed, so it did not automatically rebuild the interface. When I returned the increment operation inside setState(), the counter and progress indicator updated properly again.

activity3

Remove Expanded from one StatBox and describe what happens in your answers file, then put it back.
Answer: When I removed Expanded from one of the StatBox widgets, the layout no longer distributed the available space in the same way. The boxes could appear uneven, and an overflow might occur depending on the layout constraints. I restored Expanded afterward so the stat boxes could use the available space correctly.

activity5 

Change one setting in buildTheme(), for example the button corner radius from 8 to 20, and describe
what changed in your answers file.

Answer: I modified the Elevated button's corner radius in buildTheme() from 8 to 20. This made the button corners more curved than before. It demonstrates that adjusting the theme configuration can change the appearance of themed widgets.

Review questions

1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each
from this lab.
answer: A StatelessWidget displays content without maintaining mutable state of its own, like the profile card in Activity 1. A StatefulWidget can respond to state changes and refresh its display, as shown by the Water Tracker in Activity 2.
2. Why is a StatefulWidget written as two classes? What does each class do?
answer:Flutter separates a stateful widget into a widget class and a State class. The widget class describes the component, while the State class contains values that may change and the logic used to rebuild the interface.
3. In Activity 2, what happened when you changed _glasses outside setState()? Why?
answer: WThe water count variable could change after pressing the plus button, but the screen might continue showing the previous value. This occurred because changing the variable alone does not notify Flutter to rebuild the widget.
4. Looking at the Debug Console in Activity 2, when is build() called?
answer: TFlutter calls build() when the widget is first displayed and when a rebuild is needed. For example, calling setState() after changing the water count causes Flutter to rebuild the affected interface.
5. Explain the main axis and the cross axis of a Row and of a Column.
answer: A Row arranges its children horizontally along the main axis, with the cross axis running vertically. A Column arranges its children vertically along the main axis, while its cross axis runs horizontally.
6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?
answer: Without Expanded, one stat box no longer participated in the same flexible space distribution as the others. Depending on the constraints, the layout could become unbalanced or produce an overflow. Expanded allows a child to fill its assigned portion of the available space.
7. Why do we use GridView.builder for the menu instead of a Column with many children?
answer: GridView.builder presents menu items in rows and columns, making the menu easier to organize visually. It also creates items as needed, which can be more efficient for larger lists than placing every item inside a single Column.
8. How do Stack and Positioned create the Best seller badge in Activity 4?
answer: Stack places multiple widgets in the same visual area, allowing one widget to appear over another. Positioned specifies the badge's location within that stack, so the Best seller label can appear on top of the menu item.
9. What is the difference between customizing with ThemeData and with a style on one widget? Give
one example of each from Activity 5.
answer: ThemeData provides shared appearance settings that can affect several widgets throughout the application. For example, Activity 5 configures the overall theme and button styling. A style applied directly to a widget changes that particular widget's appearance rather than defining a shared theme setting.
10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the
change reach MaterialApp.
answer:The _ThemeDemoAppState object stores the _isDark value. When the switch is toggled, _setDark() updates that value through setState(). Flutter rebuilds the app, and MaterialApp receives the updated themeMode, switching between the light and dark themes.

