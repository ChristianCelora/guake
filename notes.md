# DO NOT PUT THIS FILE IN PULL REQ

## venv

venv was created with python3.8 and not 3.6:
```
make dev PYTHON_INTERPRETER=python3.8
```

run venv
```
pipenv shell
```

exec command in venv
```
pipenv run
```

## Bug info - Splitting terminal should not reset font size

how to reproduce:

 - open a new terminal tab (or reuse an already opened one)
 - adjust font size (CTRL + / CTRL -) changing from default
 - split the terminal tab

## Notes

- zoom in / zoom out functions are in **Guake** class in **guake_app.py** file

- split() function is in **TerminalBox** class in **boxes.py**

- increment_font_size() is in **GuakeTerminal** in **terminal.py**


when split() is called inside there is a terminal_spawn() function to create the new terminal. 
The new termial (**GuakeTerminal** instance) require a **Guake** instance
Inside the **GuakeTerminal** the *font_scale_index* is set to 0. 
It could be set to a new param inside the **Guake** instance we pass as param. 

the new param can be called *zoom* (starting from 0) that increases / decreases when Guake.zoom_in() / Guake.zoom_out() is called

### Classes

```
| RootTerminalBox
|
|
|||||||| TerminalBox (container box + scrollbar)
```

### Docs

Gtk docs:

```
https://docs.gtk.org/gtk3
```