
# @Athour : 7elmie.

    @Data : 25/04/2022 4:22 PM.

QAction               # Abstract user interface action that can be inserted into widgets

QActionGroup          # Groups actions together

QDockWidget           # Widget that can be docked inside a QMainWindow or floated as a top-level window on the desktop

QMainWindow           # Main application window

QMdiArea              # Area in which MDI windows are displayed

QMdiSubWindow         # Subwindow class for QMdiArea

QMenu                 # Menu widget for use in menu bars, context menus, and other popup menus

QMenuBar              # Horizontal menu bar

QSizeGrip             # Resize handle for resizing top-level windows

QStatusBar            # Horizontal bar suitable for presenting status information

QToolBar              # Movable panel that contains a set of controls


QWidgetAction         # Extends QAction by an interface for inserting custom widgets into action based containers, such as toolbars

QtCore                # a very powerful mechanism for seamless object communication called signals and slots (queryable and designable object properties)(hierarchical and queryable object trees that organize)(object ownership in a natural way with guarded pointers (QPointer))(a dynamic cast that works across library boundaries)

QtGui                 # The Qt GUI module provides classes for windowing system integration, event handling, OpenGL and OpenGL ES integration, 2D graphics, basic imaging, fonts and text.			

QtWidgets             # The Qt Widgets Module provides a set of UI elements to create classic desktop-style user interfaces

QMainWindow           # A main window provides a framework for building an application's user interface. Qt has QMainWindow and its related classes for main window management. QMainWindow has its own layout to which you can add QToolBars, QDockWidgets, a QMenuBar, and a QStatusBar. The layout has a center area that can be occupied by any kind of widget. You can see an image of the layout below.

QApplication          # QApplication specializes QGuiApplication with some functionality needed for QWidget-based applications. It handles widget specific initialization, finalization.For any GUI application using Qt, there is precisely one QApplication object, no matter whether the application has 0, 1, 2 or more windows at any given time. For non-QWidget based Qt applications, use QGuiApplication instead, as it does not depend on the QtWidgets library.

QWidget               # The QWidget class is the base class of all user interface objects.The widget is the atom of the user interface: it receives mouse, keyboard and other events from the window system, and paints a representation of itself on the screen. Every widget is rectangular, and they are sorted in a Z-order. A widget is clipped by its parent and by the widgets in front of it.			

QPushButton           # The push button, or command button, is perhaps the most commonly used widget in any graphical user interface. Push (click) a button to command the computer to perform some action, or to answer a question. Typical buttons are OK, Apply, Cancel, Close, Yes, No and Help.

QVBoxLayout           # This class is used to construct vertical box layout objects

QHBoxLayout           # This class is used to construct horizontal box layout objects

QMessageBox           # A message box displays a primary text to alert the user to a situation, an informative text to further explain the alert or to ask the user a question, and an optional detailed text to provide even more data if the user requests it. A message box can also display an icon and standard buttons for accepting a user response.

QTabWidget            # A tab widget provides a tab bar (see QTabBar) and a "page area" that is used to display pages related to each tab. By default

QGridLayout           # QGridLayout takes the space made available to it (by its parent layout or by the parentWidget()), divides it up into rows and columns, and puts each widget it manages into the correct cell.

QScrollArea           # A scroll area is used to display the contents of a child widget within a frame. If the widget exceeds the size of the frame

QLabel                # QLabel is used for displaying text or an image. No user interaction functionality is provided. The visual appearance of the label can be configured in various ways, and it can be used for specifying a focus mnemonic key for another widget

QListView             # A QListView presents items stored in a model, either as a simple non-hierarchical list, or as a collection of icons. This class is used to provide lists and icon views that were previously provided by the QListBox and QIconView classes, but using the more flexible approach provided by Qt's model/view architecture.

QGridLayout           # QGridLayout takes the space made available to it (by its parent layout or by the parentWidget()), divides it up into rows and columns, and puts each widget it manages into the correct cell.Columns and rows behave identically; we will discuss columns, but there are equivalent functions for rows

QScrollArea           # A scroll area is used to display the contents of a child widget within a frame. If the widget exceeds the size of the frame, the view can provide scroll bars so that the entire area of the child widget can be viewed. The child widget must be specified with setWidget().

QLineEdit             # A line edit allows the user to enter and edit a single line of plain text with a useful collection of editing functions, including undo and redo, cut and paste, and drag and drop (see setDragEnabled()).

QComboBox             # A QComboBox provides a means of presenting a list of options to the user in a way that takes up the minimum amount of screen space.A combobox is a selection widget that displays the current item, and can pop up a list of selectable items. A combobox may be editable, allowing the user to modify each item in the list.

QGroupBox             # A group box provides a frame, a title on top, a keyboard shortcut, and displays various other widgets inside itself. The keyboard shortcut moves keyboard focus to one of the group box's child widgets.

QAction               # n applications many common commands can be invoked via menus, toolbar buttons, and keyboard shortcuts. Since the user expects each command to be performed in the same way, regardless of the user interface used, it is useful to represent each command as an action.

QStandardItemModel    # QStandardItemModel can be used as a repository for standard Qt data types. It is one of the Model/View Classes and is part of Qt's model/view framework.QStandardItemModel provides a classic item-based approach to working with the model. The items in a QStandardItemModel are provided by QStandardItem.

QStandardItem         # Items usually contain text, icons, or checkboxes.Each item can have its own background brush which is set with the setBackground() function. The current background brush can be found with background(). The text label for each item can be rendered with its own font and brush. These are specified with the setFont() and setForeground() functions, and read with font() and foreground().

QFont                 # QFont can be regarded as a query for one or more fonts on the system.When you create a QFont object you specify various attributes that you want the font to have. Qt will use the font with the specified attributes, or if no matching font exists, Qt will use the closest matching installed font. The attributes of the font that is actually used are retrievable from a QFontInfo object. If the window system provides an exact match exactMatch() returns true. Use QFontMetricsF to get measurements, e.g. the pixel length of a string using QFontMetrics::width().