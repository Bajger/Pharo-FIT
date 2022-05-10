# Pharo-FIT
Obsah: Ideje, koncepty k investigaci, aby slo Pharo pouzit pro fakultni ucely a ozivit a zpopularizovat vnimani Smalltalku/Phara jakozto zastupce dynamickeho reflektivniho jazyka u studentu. Stranka zminuje radu temat, kteryma se lze zabyvat do budoucna (je potreba urcit prioritu).
_Zatim to pisu cesky, je mozne to prepsat radeji do anglictiny (pripadne udealat en verzi)_

# Vize a cile
todo

# S cim dokazu pomoci / realne zkusenosti 
- Mam odskouseny setup CI/CD (beh testu na ruznych platformach a verzich Phara) a osvojeno pouziti gitu a Githubu za pomoci Phara (Iceberg nastroje)  
- Definice tzv. projektovych baseline a reseni zavislosti mezi balicky  
- Implementace a zkusenosti command line interface za pouziti CLAP knihovny  
- Tiny Blog web applikaci, ktera byla soucasti mooc kurzu (viz zdroje), za pouziti Seaside, Bootstrap, Mongo db, Magritte meta-modelu pro validaci formularovych dat  
- Implementoval jsem a vyzkousel Pharo track cviceni (reseni ruznych jednoduchych problemu k osvojeni jazyka, vcetne mini Forth interpreta): https://exercism.org/tracks/pharo-smalltalk  
- Zkusenosti s implementaci nekterych programtatorskych problemu za pomoci Phara, tyto cviceni jsou jiz vice hardcore: https://adventofcode.com/  


# Reflektivita
Metalinky, naprosto odvazova vec -> modifikace AST a program runtimu, ktere se daji dynamick nainstalovat (behavioralni reflexe):
Slideshare: https://www.slideshare.net/MarcusDenker/lecture-metalinks  
PDF: http://marcusdenker.de/talks/18LectureMetaLinks/MetaLinks.pdf  
__Klicove video__: https://www.youtube.com/watch?v=WE_DDgBu7wA


Variable slots and fluid class definition - tothle je nahrada za ST80 instancni promenne, ktere se implementovaly pomoci stringu (symbolu) z duvodu uspory pameti na tehdejsich strojich. Pharo jde dal a umi inst. promenne deklarovat jako objekty. To ma velke dopady pro system:
http://marcusdenker.de/talks/21VariablesPharo/Variables.pdf


Observable slots (used in Spec UI). Tohle je "porozovaci slot" ktery dokaze informovat / poslat udalost pri zmene stavu. Pouzito v UI Spec frameworku v MVP/MVC: 
https://medium.com/concerning-pharo/watch-your-instance-variables-bce05250768e

Typed slots - to je ta vtipna vec, ze Pharo lze v podstate udelat jako typovany jazyk:
https://medium.com/@juliendelplanque/typed-slots-for-pharo-98ba5d5aafbe

# Pouziti / integrace s ostatnimi PL
Multi-language development using shared VM (vyhnout se tak FFI), to ma na starosti 
SW Arch. Group Hasso Plattner Institute at the University of Potsdam:  
https://arxiv.org/ftp/arxiv/papers/1803/1803.10200.pdf
PyBridge pres Pharo  

# Vyuziti v modelovani a simulaci
Open ponk modelling paper:
http://esug.org/data/ESUG2016/IWST/Papers/IWST_2016_paper_25.pdf
https://openponk.org/#contact

# Vizualizace dat
Visualizing data:
http://agilevisualization.com/

# Integrace s version control (zejmena GIT) a moznosti pro CI/CD 
Topics to include
Git an CI-CD, project baselines

# Pouziti Phara ve virtualizaci Docker
Docker and swarm of images
https://thepharo.dev/2021/02/24/running-pharo-9-in-docker/

# Soubezne zpracovani uloh
Taskit - parallelism: https://github.com/pharo-contributions/taskit
http://books.pharo.org/booklet-ConcurrentProgramming/pdf/ConcurrentProgramming.pdf
https://hal.inria.fr/hal-01353884/document

# Web a moznosti Phara s ruznymi web frameworky
Web examples
- Bootstap, Semantic UI, willow (BaSt)
- CodeParadise
- PharoJS:
- https://www.youtube.com/watch?v=2d2otdj66dw

# Nativni UI aplikace
UI pomoci GTK knihovny, bezi na headless image:

Priklad pouziti GTK aplikace a Roassal vizualizace dohromady:


# Pharo v IoT a moznosti pro senzory v zarizenich
Pharo IoT - projekt zabyvajici se problematikou IoT za pouziti Phara. 
http://www.pharoiot.org/

Nicmene je tam potreba udelat nejakou udrzbu za zastarale knihovny, Je zde nutna nahrada za wiringPi knihovnu, ktera je deprekovana. 
Kontext o problemech je zde: https://github.com/robvanlopik/Pots/blob/main/Future0f-PharoThings  
Update PharoThings (zaklad pro PharoIoT), ktery je nutno vyzkouset je zde: https://github.com/robvanlopik/Pots  
- melo by umet PiGPIO, Picod and Firmata. Take to umi FFI-based SerialPort driver. Nutne vyzkouset.



# Dulezite zdroje
Massive online course - vec podle ktere jsem si Pharo ozivil a pochopil par veci navic, velmi pekne udelano a jsou tam prakticke cviceni:  
https://mooc.pharo.org

Awesome Pharo -> __jeden s referencnich a naprosto klicovych zdroju__, prehled o dostupnych knihovnach:
https://github.com/pharo-open-documentation/awesome-pharo

Knihy vydavne zejmena Stefanem Ducasse, nektere jsou cerstve zaktualizovane, jine by zaslouzily update:
http://books.pharo.org/

Posledni dostupna konference o Pharu a prezentace o ruznych pouzitich.  Ucastnil jsem se virtualne take (demonstrace Pharo launcher cmd-line):
https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/


# Mozna anotace kurzu 
Abilities:
Ability to quickly prototype idea and fix potential program issues by using live immersive environment.

Goals:
Learn about concepts of pure object oriented (message oriented) and fully reflective dynamic languages.
Introduce a history of Smallltalk and impact to SW industry: terms like IDE, unit tests and TDD (test driven development), XP, anonymous functions (lamdas ~ lexical closures).
Learn about ability to modify a program on fly during runtime. 
Introduce pure object oriented system Pharo - a modern implementation of reflective and pure OO language based on Smalltalk80. 
Learn why image based approach is again popular (ie. Docker technology), what is benefit of shared object memory: joining source code and program runtime.

Learn about debugger-driven development and immediate program feedback.
Introduce meta-programming in Pharo using metalinks and modify a program by changing AST.
Learn about examples in SW industry and research (Visualization, IoT, usage in Aerospace, web stack). 
Learn how Pharo can be integrated with other systems (written in other programming languages) and how to integrate with VCS (i.e. Github) and CI/CD setup including test coverage.
