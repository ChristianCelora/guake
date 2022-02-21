# DO NOT PUT THIS FILE IN PULL REQ

## Bug info - Splitting terminal should not reset font size

how to reproduce:

 - open a new terminal tab (or reuse an already opened one)
 - adjust font size (CTRL + / CTRL -) changing from default
 - split the terminal tab

## Notes

zoom in / zoom out functions are in **Guake** class in **guake_app.py** file

split function is in **TerminalBox** class in **boxes.py**
