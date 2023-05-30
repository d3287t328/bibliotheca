# This is an experiment on GPT4 to test its Latinitas by translating a completely modern engineering text,
# and one that is a classic in the field of technical writing. Source https://www.man7.org/linux/man-pages/man1/bash.1.html

# SYNTAGMA
bash [optiones] [series_commandum | liber]

# IUS
Bash est Ius (C) 1989-2022 a Fundatione Software Libero,
Inc.

# OPTIONES
Omnes optiones unius litterae, documentatae in descriptione mandati incorporati 'set', inclusa '-o', possunt uti optionibus cum concha invocatur. Praeterea, bash interpretatur sequentes optiones cum invocatur:

-c     Si optio '-c' praesens est, tunc mandata leguntur ex primo argumento non-optionis series_commandum. Si sunt argumenta post series_commandum, primum argumentum assignatur ad $0 et reliqua argumenta assignantur ad positiones. Assignatio ad $0 statuit nomen conchae, quod utitur in nuntiis monitionis et erroris.
-i     Si optio '-i' praesens est, concha est interactiva.
-l     Facit ut bash se gerat quasi invocata sit ut concha initium sessionis (vide INVOCATION infra).
-r     Si optio '-r' praesens est, concha fit restricta (vide RESTRICTED SHELL infra).
-s     Si optio '-s' praesens est, aut si nulla argumenta remanent post processum optionum, tunc mandata leguntur ex input standard. Haec optio permittit positiones ponere cum invocas concham interactivam aut cum leges input per tubum.
-D     Index omnium stringarum bis-citatarum praecedentium $ imprimetur in output standard. Haec sunt stringae quae sunt in subiecto ad translationem linguarum cum praesens locale non est C aut POSIX. Hoc implicat optionem '-n'; nulla mandata exequentur.
[-+]O [shopt_option]
              shopt_option est una optionum conchae accepta a builtin 'shopt' (vide SHELL BUILTIN COMMANDS infra). Si shopt_option praesens est, '-O' ponit valorem illius optionis; '+O' eam solvit. Si shopt_option non suppeditatur, nomina et valores optionum conchae acceptarum a shopt imprimuntur in output standard. Si optio invocandi est '+O', output monstratur in forma quae possit uti iterum ut input.
--     A '--' signat finem optionum et inhibet ulteriorem processum optionum. Quaevis argumenta post '--' tractantur ut nomina librorum et argumenta. Argumentum '-' aequiparatur '--'.

Bash etiam interpretatur numerum optionum multi-litterarum. Hae optiones debent apparere in linea mandati ante optiones uni-litterae ut recognoscantur.

--debugger
        Disponit ut profilum debugger exsequatur ante initium conchae. Activat modum extensionis debugging (vide descriptionem optionis 'extdebug' ad builtin 'shopt' infra).
--dump-po-strings
        Aequiparatur ad -D, sed output est in forma libri obiecti portabilis (portable object) GNU gettext.
--dump-strings
        Aequiparatur ad -D.
--help Monstrat nuntium usus in output standard et exit cum successu.
--init-file liber
--rcfile liber
        Exsequit mandata ex libro pro loco initializationis personalis standard ~/.bashrc si concha est interactiva (vide INVOCATION infra).
--login
        Aequiparatur ad -l.
--noediting
        Non utitur bibliotheca GNU readline ad legendas lineas mandatorum cum concha est interactiva.
--noprofile
        Non legit vel systematis initium liber /etc/profile vel ullus ex initializatione personalis libris ~/.bash_profile, ~/.bash_login, or ~/.profile. Per default, bash legit hos libros cum invocatur ut concha initium sessionis (vide INVOCATION infra).
--norc Non legit et exsequit initializationis personalis liber ~/.bashrc si concha est interactiva. Haec optio est activa per default si concha invocatur ut sh.
--posix
        Mutat modum operandi bash ubi operatio default differt a norma POSIX ad conveniendum normae (modus posix). Vide SEE ALSO infra pro referentia ad documentum quod detegit qualiter modus posix afficit modum operandi bash.
--restricted
        Concha fit restricta (vide RESTRICTED SHELL infra).
--verbose
        Aequiparatur ad -v.
--version
        Monstrat informationem versionis huius instantiae bash in output standard et exit cum successu.

### ARGUMENTA
Si argumenta supersunt post processum optionis, et neque -c neque -s optio tradita est, argumentum primum ut nomen libri mandata testudinis continentis accipitur.

Si bash hoc modo invocatur, $0 ad nomen libri figitur, et parametri positionales ad argumenta reliqua instituuntur. 

Bash ex hoc libro mandata legit et exsequitur, deinde exibit. Exitus Bash est exitus ultimi mandati in scripto exsecuti. 

Si nulla mandata exsequuntur, status exitus est 0. Primum conatur...

### INVOCATIO
Concha initium sessionis est una cuius primus character argumenti zero est "-", aut una incepta cum optio --login.

Concha interactiva est una incepta sine argumentis non-optionis (nisi -s specificatur) et sine optio -c, cuius input et error standard utrumque ad terminales connectuntur (ut per isatty(3) determinatur), aut una incepta cum optio -i. 

PS1 instituitur et $- includit 'i' si bash est interactiva, licentiam dando scripto conchae aut libro initii sessionis hunc statum probare.

Paragraphi sequentes describunt quomodo bash libros initii sessionis suos exsequitur. Si ullus ex libris existit sed non potest legi, bash errorem nuntiat. 

Tildae in nominibus librorum ut infra in sectione EXPANSIO sub Tilde Expansion describitur expanduntur.

Cum bash vocatur ut concha initii sessionis interactiva, aut ut concha non interactiva cum optio --login, primo legit et exsequit mandata ex libro /etc/profile, si ille liber existit. Post lectionem illius libri, quaerit ~/.bash_profile, ~/.bash_login, et ~/.profile, in illo ordine, et legit et exsequit mandata ex primo qui existit et legibilis est. Optio --noprofile potest adhiberi cum concha incohat ut hoc comportamentum inhibeat.

Cum concha initii sessionis interactiva exit, aut concha initii sessionis non interactiva mandatum exit incohat, bash legit et exsequit mandata ex libro ~/.bash_logout, si ille existit.

Cum concha interactiva quae non est concha initii sessionis incipit, bash legit et exsequit mandata ex ~/.bashrc, si ille liber existit. Hoc potest inhiberi adhibendo optionem --norc. Optio --rcfile liber cogeret bash ut mandata ex libro, non ex ~/.bashrc, legeret et exsequeretur.

Cum bash incohat non interactiviter, ad scriptum conchae, exempli gratia, perficiendum, quaerit variabile BASH_ENV in ambiente, expandit eius valorem si ibi appareat, et utitur valore expanso ut nomine libri ad legendum et exsequendum. Bash se gerit quasi sequens mandatum exsequeretur: if [ -n "$BASH_ENV" ]; then . "$BASH_ENV"; fi, sed valor variabilis PATH non adhibetur ad nomen libri quaerendum.

Si bash invocatur cum nomine sh, conatur imitari comportamentum initii versionum historicarum sh quam proxime possibile, dum ad normam POSIX conformit. Cum invocatur ut concha initii sessionis interactiva, aut concha non interactiva cum optio --login, primo conatur legere et exsequi mandata ex /etc/profile et ~/.profile, in illo ordine. Optio --noprofile potest adhiberi ut hoc comportamentum inhibeat. Cum invocatur ut concha interactiva cum nomine sh, bash quaerit variabile ENV, expandit eius valorem si definitum est, et utitur valore expanso ut nomine libri ad legendum et exsequendum. Cum concha invocatur ut sh non conatur legere et exsequi mandata ex ullis aliis libris initii, optio --rcfile nullum effectum habet. Concha non interactiva invocata cum nomine sh non conatur legere ullum alium librum initii. Cum invocatur ut sh, bash intrat in modum posix postquam libri initii lecti sunt.

Cum bash incohat in modo posix, ut cum optione mandati --posix, sequitur normam POSIX pro libris initii. In hoc modo, conchae interactivae expandunt variabile ENV et mandata leguntur et exsequuntur ex libro cuius nomen est valor expansus. Nulli alii libri initii leguntur.

Bash conatur determinare cum curritur cum suo input standard connecto ad connexionem retis, ut cum exsequitur a daemonio historico conchae remotae, plerumque rshd, aut a daemonio conchae securae sshd. Si bash determinat se currere non interactiviter in hoc modo, legit et exsequit mandata ex ~/.bashrc, si ille liber existit et legibilis est. Hoc non faciet si invocatur ut sh. Optio --norc potest adhiberi ut hoc comportamentum inhibeatur, et optio --rcfile potest adhiberi ut cogeret alium librum legi, sed neque rshd neque sshd generaliter invocant concham cum illis optionibus aut permittunt eas specificari.

Si concha incipit cum effectivo id utentis (gruppi) non aequale ad reale id utentis (gruppi), et optio -p non adhibetur, nulli libri initii leguntur, functiones conchae non hereditantur ex ambiente, variables SHELLOPTS, BASHOPTS, CDPATH, et GLOBIGNORE, si appareant in ambiente, negliguntur, et effectivum id utentis ponitur ad reale id utentis. Si optio -p adhibetur in invocatione, comportamentum initii est idem, sed effectivum id utentis non restituitur.

