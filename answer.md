activity2

Experiment: inside _addGlass, move _glasses++ outside of setState and tap +. Write down what
happens in your answers file, then put it back.
Answer: When I moved _glasses++ outside setState() and tapped the + button, the water count changed in the variable, but the user interface did not update immediately. This happened because Flutter was not notified to rebuild the widget. After putting _glasses++ back inside setState(), the water count and progress indicator updated correctly.

activity3

Remove Expanded from one StatBox and describe what happens in your answers file, then put it back.
Answer: When I removed Expanded from one StatBox, the layout became uneven because the stat boxes no longer shared the available space equally. Depending on the available space, it could also cause a layout overflow. Expanded helps the widgets occupy their allocated space in the Row. After observing the result, I put Expanded back to restore the layout.

activity5 

Change one setting in buildTheme(), for example the button corner radius from 8 to 20, and describe
what changed in your answers file.

Answer: I changed the button corner radius in buildTheme() from 8 to 20. As a result, the Elevated button's corners became more rounded. This shows how changing a theme setting can customize the appearance of the app's buttons.

Review questions

1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each
from this lab.
answer: A StatelessWidget does not manage changing state, such as the profile card in Activity 1. A StatefulWidget can update its interface when its state changes, such as the Water Tracker in Activity 2.
2. Why is a StatefulWidget written as two classes? What does each class do?
answer: A StatefulWidget uses two classes because they have different responsibilities. The widget class defines the widget, while the State class stores changing data and updates the interface using setState().
3. In Activity 2, what happened when you changed _glasses outside setState()? Why?
answer: When I moved _glasses++ outside setState() and tapped the + button, the interface did not update immediately. This happened because Flutter was not notified to rebuild the widget.
4. Looking at the Debug Console in Activity 2, when is build() called?
answer: The build() method is called when Flutter creates the interface and whenever the widget needs to rebuild, such as after calling setState() to update the water count.
5. Explain the main axis and the cross axis of a Row and of a Column.
answer: In a Row, the main axis is horizontal and the cross axis is vertical. In a Column, the main axis is vertical and the cross axis is horizontal.
6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?
answer: When I removed Expanded, the stat boxes no longer shared the available space equally, and the layout could become uneven or overflow. Expanded allows a widget to occupy its allocated share of the available space.
7. Why do we use GridView.builder for the menu instead of a Column with many children?
answer: We use GridView.builder because it displays menu items in a grid and can build items as needed. It is more suitable for a menu with multiple items than a Column.
8. How do Stack and Positioned create the Best seller badge in Activity 4?
answer: Stack allows widgets to overlap, while Positioned controls the badge's location. Together, they place the Best seller badge over the menu item.
9. What is the difference between customizing with ThemeData and with a style on one widget? Give
one example of each from Activity 5.
answer: ThemeData customizes the appearance of widgets throughout the app. For example, Activity 5 uses ThemeData to configure the app theme. A widget-specific style customizes an individual widget, such as changing the Elevated button's corner radius to 20.
10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the
change reach MaterialApp.
answer: The _ThemeDemoAppState class holds the _isDark variable. When the switch changes, _setDark() calls setState(), rebuilding the app and updating MaterialApp's themeMode to use the light or dark theme.
