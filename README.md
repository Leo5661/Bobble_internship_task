# Bobble Internship Task Reverse Engineering
In this task we have an apk of Marathi Keyboard and this app also have a feature of English ==> Marathi transliteration.
it uses a map of english to marathi words to achieve that. 

## Task
- The task was to find and extract the mapping file. 
- Convert it to human readable csv format.

## Process to get the file
- First step is to get the apk of the app and in this task the apk is provided.
- Now I have the apk the first step is to work on extracting some of the initial info of the app by just converting the extension from <b>".apk"</b> to the <b>".zip"</b> format to read the file it contains.
- As it open first thing I looked for is library as in the task it's given that it's a map file so I start find different file which it have in the lib folder, In this folder it have <b>"libjni_manglish.so"</b> file from name it looks like that this file have some link with the feature, but this is a <b>"shared object"</b> file it's very hard to read it(nearly impossible). 
- As in the task it's map file so it must be in the file not in the jave/kotlin code, so I again looked for the file in the extracted folder one by one from zip, in the assets folder I found a database file <b>"manglish_db.db"</b> same name as the library.
- I used <b>DB Browser for SQLite</b> to open <b>"manglish_db.db"</b> file, this file contains two tables name <b>"sqlite_sequence"</b> and <b>"word_map_phone"</b>.
- The <b>"word_map_phone"</b> table have the list of the word what I'm finding. I crossed checked using app by typing the english word and obtaining the marathi word for it. This is the table of the map.
- Now using the <b>DB Browser for SQLite</b> I extracted the data of the table and converted it into the <b>".csv"</b> format for human readable form.
