The debug GUI is a way for the user to control the arm via buttons on the screen

## Setup
To open the GUI run these commands:
```
cd ~/PythonArmControl
```
```
cd tests
```
```
python gui.py
```

This should be the window that appears
![[Debug_GUI.png]]

The number in the middle represents the angle increment that the arm moves in, this increment can be increased with the **Speed Down** and **Speed Up** buttons

Also while controlling the arm through the GUI, note that the buttons will turn yellow while a command is running and will change back the the default light gray after finishing.

Make sure you wait for a command to finish before pressing another button, otherwise it will start stacking commands for the arm causing unwanted motion.