# Pharo-FIT
Obsah: Ideje, koncepty k investigaci, aby slo Pharo pouzit pro fakultni ucely a ozivit a zpopularizovat vnimani Smalltalku/Phara jakozto zastupce dynamickeho reflektivniho jazyka u studentu. Stranka zminuje radu temat, kteryma se lze zabyvat do budoucna (je potreba urcit prioritu).
_Zatim to pisu cesky, je mozne to prepsat radeji do anglictiny (pripadne udealat en verzi)_

# Vize a cile
- nakopnout studenty v zajmu o dyn. jazyky (konkretne Pharo) a ukazat, ze to ma moderni vyuziti v SW prumyslu a prakticke vyuziti pro ne do budoucna
- identifikovat zajimave domeny, ktere fakulta nebo ustav resi a kde by Pharo mohlo byt vhodny nastroj
- dobrovolna druzba s ostatnimai univerzitami, kde se Pharo vyuziva a identifikovat potencialni spolecne projekty, na kterych by studenti/skola mohla participovat 

# Par prepodkladu k dalsimu rozvoji
1) Uvedomuju si, ze pocatecni nadseni muze brzy vyprchat a cele to muze vyjit s pouzitim Smaltalku (Phara) na fakulte naprazdno. Je tezke dodelat veci do konce (nez s nima zacinat). Proto je smysluplnejsi omezit pocet temat, kterym se venovat (nebo je prioritizovat ve fronte) a ty postupne rozvijet s rozumnymi ocekavanimi. 
2) Pravdepodobne je dobre s vami udrzovat pravidelny kontakt, rozpravu o aktivitach ve Snalltalku, reseni problemu se kterymi si lze vzajemne pomoci.
3) S celou radou veci dokazu byt napomocen. Artefakty (vcetne kodu) bych zachytil v tomto repositari (ktery lze zprivatizovat, aby nebyl verejny) a ten muze slouzit jako odrazovy mustek pro zadani dipl. praci (nebo i jinych projektu), pripadne nove struktury, obsahu pro kurz Dynamicke jazyky.

# S cim dokazu pomoci / realne zkusenosti 
- Mam odskouseny setup CI/CD (beh unit testu na ruznych platformach a verzich Phara, test coverage report) a osvojeno pouziti gitu a Githubu za pomoci Phara (Iceberg nastroje)  
- Definice tzv. projektovych baseline a reseni zavislosti mezi balicky -> toto je nutne, aby se projekt nahral vcetne vsech zavislosti v jinych repositarich
- Implementace a zkusenosti command line interface za pouziti CLAP knihovny  
- Tiny Blog web applikaci, ktera byla soucasti mooc kurzu (viz zdroje), za pouziti Seaside, Bootstrap, Mongo db, Magritte meta-modelu pro validaci formularovych dat. Je to takova ucelena ukazka Seaside web aplikace: https://books.pharo.org/tinyblog-tutorial/book/TinyBlogEN-gitc55a88d.pdf  
- Implementoval jsem a vyzkousel Pharo track cviceni (reseni ruznych jednoduchych problemu k osvojeni jazyka, vcetne mini Forth interpreta): https://exercism.org/tracks/pharo-smalltalk  
- Zkusenosti s implementaci nekterych programtatorskych problemu za pomoci Phara, tyto cviceni jsou jiz vice hardcore: https://adventofcode.com/  
- Pouzivani HTTP klienta (GET/POST requesty) ze Zinc knihovny (napr. pri dotazovani na Github.com)
- Serializace dat, format STON a Tonel (pro export cele tridy), NeoJSON, 

# Obecna vize a smerovani Phara
Zminuji zde par veci, co se komunita Phara snazi dosahnout, v podstate roadmap prezentace Stephana Ducasse a jeho lidi z Inria institutu. 

Detaily zde: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day1/2-Pharo10-Ducasse.pdf

Pharo 10 (soucasny latest stable release):  
- modularizace (minimalni image)
- VM optimalizace a zrychleni
- smazano 48K LOC (zmenseni image)

Pharo 9 (vycuc toho nejdulezitejsiho): 
- Kompletni redesign UI frameworku do Spec2 frameworku (jakasi obalka, ktera muze stridat UI backendy), pridani moznosti pro GTK backend ve headless modu
- prepsani nastroju (debugger, inspector, playground) do Spec2
- zrychleni a optimalizace na urovni VM a kompilatoru
- VM v idle modu (nebere CPU time)
- podpora arm64
- atd.

Shrhnuti uprav v soucasnem VM. Velmi zajimave, je to vyssi divci pro me. Zminuji tam novy tzv. "perm space" objektovou pamet pro objekty co se nemeni: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day1/3-VM-Tesone_Polito.pdf

Jakym zpusobem podavat do budoucna enhancementy __(treba kdyby neco potrebovala fakulta)__ do Phara: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day1/7-PhEPs-Lorenzano.pdf


# Osobnosti a jejich tvorba
TODO



# Reflektivita
Metalinky, naprosto odvazova vec -> modifikace AST a program runtimu, ktere se daji dynamicky nainstalovat (behavioralni reflexe):
Slideshare: https://www.slideshare.net/MarcusDenker/lecture-metalinks  
PDF: http://marcusdenker.de/talks/18LectureMetaLinks/MetaLinks.pdf  
__Klicove video (alespon pro me)__: https://www.youtube.com/watch?v=WE_DDgBu7wA


Variable slots and fluid class definition - tothle je nahrada za ST80 instancni promenne, ktere se implementovaly pomoci stringu (symbolu) z duvodu uspory pameti na tehdejsich strojich. Pharo jde dal a umi inst. promenne deklarovat jako objekty. To ma velke dopady pro system:
http://marcusdenker.de/talks/21VariablesPharo/Variables.pdf


Observable slots (used in Spec UI). Tohle je "porozovaci slot" ktery dokaze informovat / poslat udalost pri zmene stavu. Pouzito v UI Spec frameworku v MVP/MVC: 
https://medium.com/concerning-pharo/watch-your-instance-variables-bce05250768e

Typed slots - to je ta vtipna vec, ze Pharo lze v podstate udelat jako typovany jazyk:
https://medium.com/@juliendelplanque/typed-slots-for-pharo-98ba5d5aafbe

Jak vytvorit anonymni tridu pro spehovani (slide 16): http://rmod-pharo-mooc.lille.inria.fr/MOOC/PharoMOOC/Week7/C019-W7S04-OtherReflective.pdf

Anonymous visitor, zajimave zpusoby generovani/kompilovani kodu: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/ShowUsYourProjects/1-showUsAnonymousVisitor.pdf

# Pouziti / integrace s ostatnimi PL a jinymi aplikacemi
## Multi-language development za pouziti "sdilene" VM 
Je mozne se vyhnout pouziti FFI, to ma na starosti SW Arch. Group Hasso Plattner Institute at the University of Potsdam:  
https://arxiv.org/ftp/arxiv/papers/1803/1803.10200.pdf

Jak udelat Pharo jako binarni aplikaci a jak integrovat s jinou existujici aplikaci, zle pouzit VM jako DLL:
https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day1/10-BrandingPharo-Tesone_Polito.pdf

## PyBridge pres Pharo
Integrace s Python PL  
Repositar zde: https://github.com/ObjectProfile/PythonBridge  
Nebo take (vice informaci): https://objectprofile.github.io/PythonBridge/  
  

__UFFI__  
Volani pres foreign function interface. Zde doslo k vyraznemu zlepseni od core Pharo vyvojaru (threaded FFI):  
- detaily zde: https://hal.inria.fr/hal-03358607/document     
- kniha: http://books.pharo.org/booklet-uffi/  

# Vyuziti v modelovani a simulaci
Open ponk modelling paper:
http://esug.org/data/ESUG2016/IWST/Papers/IWST_2016_paper_25.pdf  
https://openponk.org/  
Zdarila ukazka modelovaci platformy OpenPonk: https://www.youtube.com/watch?v=_gQgXdJyr-0  
Petriho site: https://github.com/OpenPonk/petrinets  

# Vizualizace dat
Visualizace pomoci Roassal knihovny, je zde spousta prikladu a vizualizace jsou nekdy uchvacujici a prakticke pri nejake analyze dat. Je to takova obdoba d3js, ale s tou vyhodou, ze data (model) ktery vizualizujete mate primo live v imagi a muzete menit semantiku pro zobrazeni on-the-fly:
http://agilevisualization.com/  

Umi to i 3D: https://www.youtube.com/watch?v=CuimMwuZiGA  
Par dechberoucich ukazek (ze pry je Smalltalk dead :) ): https://youtu.be/R2rLr7Z1b8Y  
Delsi prednasky: https://youtu.be/-Pk4q5oMdLo  
teaser: https://vimeo.com/293060446  

Pouziti Roassal knihovny a GTK UI backendu: (Tweet o Pavlovi Krivankovi): https://twitter.com/estebanlm/status/1129367357451886592  
Slidy z jednoho z hlavnich vyvojaru: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Workshop/2-ExtendingTheEnvironment-MamaniTorres.pdf  
Repositar: https://github.com/ObjectProfile/Roassal3  

# Vyvoj her a HW akcelerace pres Woden engine
Je zde par ukazek jak delat 3d scenu (HW akcelerovanou): https://www.youtube.com/watch?v=zJAjDSg-nvU  
Repositar s ukazkama zde: https://github.com/ronsaldo/woden-core-examples  
Isometricky engine: https://github.com/psvensson/golgotterath  
Ukazky 2d her od tymu z Jizni Ameriky (Ba-St): https://github.com/apiorno/Winter-Examples  


# Integrace s version control (zejmena GIT) a moznosti pro CI/CD 
Projektove zavislosti, jak to cele funguje: https://github.com/pharo-open-documentation/pharo-wiki/blob/master/General/Baselines.md  
Git a pouzivani Iceberg (git klient ve Pharu, udrzuje image v syncu s Git repositarem): http://books.pharo.org/booklet-ManageCode/pdf/2020-05-12-ManageCode.pdf  

__CI/CD:__ 
Lze pomoci Github actions (pekne popsano zde): https://github.com/hpi-swa/smalltalkCI 
Nebo Jenkins serveru: TODO

# IDE a vyvojove prostredi
Krome standartniho Phara image se da vyvijet pomoci tzv. Glamorous toolkitu vyvijeno firmou Feenk. Jejich cilem je se spopularizovat a pouzit i v jinych jazicich (filozoficky jakasi nahrada/pokracovani za Emacs - viz [tato diskuze](https://www.reddit.com/r/emacs/comments/lbwff7/glamorous_toolkit_a_smalltalk_take_on_some_ideas/)
Odkaz na Gtoolkit videa: https://www.youtube.com/channel/UClLZHVq_-2D2-iI4rA2O8Ug/featured  
stranky spolecnosti ktera to vyvinula: https://feenk.com/  

# Pouziti Phara ve virtualizaci Docker
Docker and swarm of images - jak to pouzivaji ve 2denker.com: https://www.youtube.com/watch?v=Ncdrk5Bd9fY   
Pouziti Dockeru a deployment web aplikace: https://thepharo.dev/2021/02/24/running-pharo-9-in-docker/  

# Soubezne zpracovani uloh
Taskit - parallelism: https://github.com/pharo-contributions/taskit  
http://books.pharo.org/booklet-ConcurrentProgramming/pdf/ConcurrentProgramming.pdf  
https://hal.inria.fr/hal-01353884/document  

# Web a moznosti Phara s ruznymi web frameworky
Co se tyka webu, zaznamenal jsem v podsate 3 pristupy: 

## 1. Minimalni image bezici v prohlizeci (velikost cca 200kB) a interpret Squeak JS
Ma to na starosti firma ObjectGuild z Belgie, snazi se to za chvili vydat jako betu pro sirsi pouziti (Zalozeno na CodeParadise, coz je v podstate vice experimentalni knihovna vyvinuta jednim z tvurcu). Zde SqueakJS oznacuje VM v podstate napsany v Javascriptu a interpretuje minimalni Pharo image, ktera slouzi s komunikaci pres web sockety s backend-image:
Video z prezentace o frameworku: https://vimeo.com/457353130  
https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day1/5-ExpressiveSystems-Stel-Alteren.pdf  
https://github.com/ErikOnBike/CodeParadise/blob/master/introduction.md  
Odkaz na novou verzi frameworku od ObjectGuild: TODO soon


## 2. Seaside framework s Jquery knihovnou
Asi nejrozsirenejsi zpusob. Seaside je komponent based stateful web framework, generuje veskery obsah web stranky (pres tzv. html canvas). Generuje to HMTL+css ze smalltalku kodu. Komunikace je pres Ajax a JQuery.

__Bootstap__ - pouziti Saasidu s boostrap frameworkem: https://github.com/astares/Seaside-Bootstrap5  

__Semantic UI a Willow (BaSt)__  
  Willow je jakasi abstraktni vrstva, kterou nezajima jaky framework se zrovna pouziva (pouziva to firma Mercap, ktera to dala jako opensource). Jejich cilem je usnadnit psani Ajax interakci mezi klientem (prohlizecem) a server casti, ukazka zde: https://www.youtube.com/watch?v=U6-JoPRcXHc  
repositar zde: https://github.com/ba-st/Willow  

- Material design lite se Seasidem: https://github.com/DuneSt/MaterialDesignLite  


## PharoJS  - transpilator z Phara do JS
Kladou si za cil vubec JS nepouzivat, pouze do nej exportovat jak pro klientskou stranu tak pro server: prednaska zde: https://youtu.be/2d2otdj66dw  
Slidy zde: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day2/7-PharoJSClientServer-Bouraqadi.pdf
Hlavni stranka: https://pharojs.org

# Nativni UI aplikace
UI pomoci GTK knihovny, bezi na headless image.
__Priklad pouziti headless GTK aplikace a Roassal vizualizace dohromady, pouziva [Cairo backend](https://en.wikipedia.org/wiki/Cairo_(graphics))__: https://rmod-files.lille.inria.fr/Videos/fosdem/gtk-spec-live.mp4  

APart form editor - je editor pro UI, ktery vygeneruje specifikaci - prace Pavla Krivanka, ktery to vyvyji pro nemeckou firmu:
https://github.com/bauing-schmidt/APart  
Slidy: https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day2/4-ApartFormEditor-Krivanek.pdf


# Pharo v IoT a moznosti pro senzory v zarizenich
Pharo IoT - projekt zabyvajici se problematikou IoT za pouziti Phara. 
http://www.pharoiot.org/
Hlavni repositare: https://github.com/pharo-iot

Web popisuje urcity postup, nicmene je tam potreba udelat nejakou udrzbu za zastarale knihovny, Je zde nutna nahrada za wiringPi knihovnu, ktera je deprekovana. 
Kontext o problemech je zde: https://github.com/robvanlopik/Pots/blob/main/Future0f-PharoThings  
Update PharoThings (zaklad pro PharoIoT), ktery je nutno vyzkouset je zde: https://github.com/robvanlopik/Pots  
- melo by umet PiGPIO, Picod and Firmata. Take to umi FFI-based SerialPort driver. Nutne vyzkouset.

# Komunikace a sitovy prenos
AMQP klient pro Pharo https://github.com/ba-st/Ansible (AMQP broker je patrne robustnejsi/pomalejsi nez Kafka)
Zinc HTTP server a klient: https://github.com/svenvc/zinc
tbd.

# Umela inteligence a Machine learning
Toto prilis nemam prozkoumano, nicmene stav podpurnych knihoven by mel byt v dobrem stavu, komunita se snazi o komplement (napr. Polymath, Dataframe) k Python knihovnam. Rekl bych, ze je tu rada prilezitosti napsat nejaky chybejici algoritmus, bud jako bakalarskou nebo dimpl. praci:
https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/Day1/8-PharoAI-Jordan-Zaitsev.pdf
https://github.com/pharo-ai/wiki
https://github.com/pharo-ai/awesome-pharo-ml


# Dulezite zdroje
Massive online course - vec podle ktere jsem si Pharo ozivil a pochopil par veci navic, velmi pekne udelano a jsou tam prakticke cviceni:  
https://mooc.pharo.org

__Awesome Pharo__  
-> __jeden s referencnich a naprosto klicovych zdroju__, prehled o dostupnych knihovnach:
https://github.com/pharo-open-documentation/awesome-pharo

Buenos Aires Smalltalk - velmi ceneny zdroj knihoven a nastroju z Jizni Ameriky 
https://github.com/ba-st

Knihy vydavne zejmena Stefanem Ducasse, nektere jsou cerstve zaktualizovane, jine by zaslouzily update:
http://books.pharo.org/

__PharoDays__  
Konference o Pharu a prezentace o ruznych pouzitich.  Ucastnil jsem se virtualne take (demonstrace Pharo launcher cmd-line):
https://rmod-files.lille.inria.fr/Team/PharoPresentations/2022-Pharodays/  

__[Discord server](https://discord.gg/QewZMZa)__
V podstate interaktivnejsi nahrada za mailing listy, nebo spis doplnek. Je zde vyhledavani ve fulltextu, je mozne ze podobny problem jiz zde nekdo resil a lze tak dohledat konverzaci o problematice.  

+ tradicni mailing listy.


# Namet pro novy obsah (anotace, napln) kurzu Dynamicke jazyky
Tohle je potreba ucesat a prepsat a dat tomu trochu rad. Jen co me v podstate napadlo behem par minut.
Cilem je take postavit seznam cviceni, ktere by mohly ukazat na prakticke dopady ve vyuzivani at uz pri skolnich nebo i profesionalnich projektu/produktu. 

## Anotace 
Abilities:
- Ability to quickly prototype idea and fix potential program issues by using live immersive environment.

__Goals of course:__
- Learn about concepts of pure object oriented (message oriented) and fully reflective dynamic languages.
- Introduce a history of Smallltalk and impact to SW industry: terms like IDE, unit tests and TDD (test driven development), XP, anonymous functions (lamdas ~ lexical closures).
- Learn about ability to modify a program on fly during runtime. 
- Introduce pure object oriented system Pharo - a modern implementation of reflective and pure OO language based on Smalltalk80. 
- Learn why image based approach is again popular (ie. Docker technology), what is benefit of shared object memory: joining source code and program runtime.

__Benefits for students:__  
- Learn about debugger-driven development and immediate program feedback.
- Avoid unnecessary code complexity and maximize reusability due to Smalltalk idiomatic way of writing code. 
- Improve SW design skills by using OO narratives and real-life examples (Don't think how SW works, think how real world works).
- Introduce meta-programming in Pharo using metalinks and modify a program by changing AST.
- Learn about examples in SW industry and research (Visualization, IoT, usage in Aerospace, web stack). 
- Learn how to integrate existing SW (in Pharo) with other systems (written in other programming languages) and how to develop with VCS (i.e. Github) and CI/CD setup including test coverage.

## Obsah cviceni
TODO 

## Teoreticky obsah - prednasky
TODO
