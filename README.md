# QuickNotes 📝

A simple tool for accessing, storing and creating single lined notes!

## Overview

QuickNotes is a CLI-based that allows users to manage short single-line notes. With QuickNotes, users can create collections of notes, open and view them, add new notes, or remove existing notes.

Storing notes happens locally. For each collection a plain text file is created. Inside of the text file every new line is a new note.

## Getting Started

### Installing

* Simply head to [releases](https://gitea.kood.tech/jerejuhanimeskanen/notes/releases) and download the latest build!

### Building 
<!> [Go](https://go.dev/doc/install) is required for building, instructions to install can be found on their website.

* If you want to make changes to your specific build, clone the repository, make changes and build it yourself.
```
git clone https://gitea.kood.tech/jerejuhanimeskanen/notes.git
cd notes
go build
```

## Usage

### Running the file

```
./quicknotes ExampleCollection
```

### Selecting operation

Selecting an option wheteer to show, add or delete some notes!
```
Welcome to QuickNotes!
You are currently managing: ExampleCollection

Select operation:
1. Show notes.
2. Add a note.
3. Delete a note.
4. Exit.
```

### Showing notes

When selected, tool will show all notes in current collection.
```
Notes in ExampleCollection:
001 - note one
002 - note two
```


### Adding a note

When selected, tool will prompt for an input, then add the note to current collection!
```
Enter the note you'd like to add:
note three
```


### Deleting a note

When selected, tool will prompt user to give the index of a note to remove. Or optionally use 0 to cancel out.
```
Notes in ExampleCollection:
001 - note one
002 - note two
003 - note three

Which note you'd like to remove? 0 to exit:
3
```

## Known bugs 🐛
* Ability to create empty notes with the use of terminal keys e.g. ^[[D

## Authors
* **Jere Meskanen** - *Managing collections & notes* - [jerejuhanimeskanen](https://gitea.kood.tech/jerejuhanimeskanen)
* **Ahmed El Maazi** - *Navigation, handling user inputs* - [ahmedelmaazi](https://gitea.kood.tech/ahmedelmaazi)
* **Chanrow Petch** - *Handling & validating arguments* - [chanrowpetch](https://gitea.kood.tech/chanrowpetch)
