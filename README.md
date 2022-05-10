# Pharo-FIT
Obsah: Ideje, koncepty k investigaci, aby slo Pharo pouzit pro fakultni ucely a ozivit a zpopularizovat vnimani Smalltalku/Phara jakozto zastupce dynamickeho reflektivniho jazyka u studentu. Stranka zminuje radu temat, kteryma se lze zabyvat do budoucna (je potreba urcit prioritu).
_Zatim to pisu cesky, je mozne to prepsat radeji do anglictiny (pripadne udealat en verzi)_

# Vize a cile
todo


# Reflektivita
Metalinks (modifying AST and program runtime - behavioral reflection):
Slideshare: https://www.slideshare.net/MarcusDenker/lecture-metalinks
PDF: http://marcusdenker.de/talks/18LectureMetaLinks/MetaLinks.pdf
black magic metalinks:
https://www.youtube.com/watch?v=WE_DDgBu7wA


Variable slots and fluid class definition:
http://marcusdenker.de/talks/21VariablesPharo/Variables.pdf

Observable slots (used in Spec UI):
https://medium.com/concerning-pharo/watch-your-instance-variables-bce05250768e

Typed slots :)
https://medium.com/@juliendelplanque/typed-slots-for-pharo-98ba5d5aafbe

# Pouziti / integrace s ostatnimi PL
Multi-language development using shared VM (to avoid FFI):
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
UI in GTK
GTK a Roassal dohromady

# Pharo v IoT a moznosti pro senzory v zarizenich
Pharo IoT
- 
Awesome Pharo
http://books.pharo.org/
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
