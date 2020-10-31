## Angriffe auf WhatsApp, Signal und Telegram in den Schlagzeilen!

Ein aktueller Pressespiegel befindet sich auf [**https://encrypto.de/news/contact-discovery**](https://encrypto.de/news/contact-discovery).

## Was ist Mobile Kontaktermittlung & Warum betrifft mich das?

Verfahren zur mobilen Kontaktermittlung (im Englischen "Mobile Contact Discovery") erlauben den Nutzer\*innen von mobilen Messengern bequem mit Personen aus ihrem Adressbuch in Kontakt zu treten. So können neu registrierte Nutzer\*innen unverzüglich Nachrichten an existierende Kontakte basierend auf deren Telefonnummern schicken, ohne mit diesen zunächst zusätzliche Kontaktinformationen wie Nutzernamen oder E-Mail Adressen austauschen zu müssen.

Einige der populärsten Messenger der Welt (mit Milliarden von Nutzer\*innen) wie [WhatsApp](https://www.whatsapp.com/) laden zur Kontaktermittlung regelmäßig [die vollständigen Adressbücher ihrer Nutzer\*innen](https://www.whatsapp.com/legal/#terms-of-service) hoch, während Messenger mit einem Fokus auf Privatsphäre wie [Signal](https://signal.org/) lediglich [kurze Hashwerte von Telefonnummern](https://support.signal.org/hc/en-us/articles/360007061452-Does-Signal-send-my-number-to-my-contacts-) übertragen oder sich auf [sichere Hardware](https://signal.org/blog/private-contact-discovery/) verlassen. Leider deutet die niedrige Entropie von Telefonnummern darauf hin, dass es sehr leicht möglich ist, solche Hashwerte umzukehren, sodass trotz aller guten Absichten [die Privatsphäre dadurch nicht geschützt wird](https://doi.org/10.18420/sicherheit2018_04).

In einer kollaborativen Zusammenarbeit der [TU Darmstadt](https://encrypto.de), der [TU Graz](https://www.iaik.tugraz.at/) und der [Universität Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/secure-software-systems-group/) zeigen wir, dass aktuell verwendete Verfahren zur mobilen Kontaktermittlung die Privatsphäre von Nutzer\*innen massiv bedrohen.

### Preisgabe Sozialer Graphen durch "Neugierige" oder Kompromittierte Dienstanbieter

Die Übertragung quasi aller persönlichen Kontakte an einen Dienstanbieter stellt ein signifikantes Risiko für die Privatsphäre und auch eine rechtliche Herausforderung dar, weil sich vom sozialen Graph von Nutzer\*innen eine Vielzahl persönlicher Informationen ableiten lässt. Insbesondere können sensible Kontaktbeziehungen bekannt und dieses Wissen dafür genutzt werden, Nutzer\*innen zu diskriminieren, zu erpressen, sie in Betrugsmaschen zu verwickeln, ihrem Ruf zu schaden oder sie das Ziel einer strafrechtlichen Ermittlung zu machen. Dienstanbieter können auch kompromittiert sein oder von Geheimdiensten gezwungen werden, Nutzerdaten auszuhändigen, was in der Preisgabe solcher sensiblen Informationen resultiert.

Bei der Installation von mobilen Messengern gefährden Nutzer\*innen auch die Privatsphäre von Personen die gar nicht bei diesem Dienst registriert sind, da [deren Kontaktinformationen ohne Zustimmung übertragen werden](https://guild.co/blog/is-whatsapp-in-breach-of-the-gdpr-a-lawyers-view/). Ein illustratives Beispiel für einen massiven Eingriff in die Privatsphäre lieferte WhatsApp, das 2014 von Facebook aufgekauft wurde und seine Datenbank mit dem Mutterunternehmen teilte: [Facebook Nutzer\*innen erhielten daraufhin Freundschaftsvorschläge für ihnen fremde Personen, die dieselbe psychiatrische Praxis aufsuchten und deren Festnetznummer gespeichert hatten](https://splinternews.com/facebook-recommended-that-this-psychiatrists-patients-f-1793861472).

### Preisgabe Persönlicher (Meta-) Daten durch Crawling Angriffe

Bösartige Nutzer\*innen oder Hacker\*innen können auch daran interessiert sein, Informationen über andere Personen zu extrahieren. Beispiele für persönliche (Meta-) Daten die üblicherweise in den Profilen von Nutzer\*innen gespeichert sind beinhalten Profilbilder, Namen, Statusnachrichten und die zuletzt online gewesene Zeit. Durch das Verfolgen solcher Daten über die Zeit hinweg ist es sogar möglich, [akkurate Verhaltensmodelle abzuleiten](https://onlinestatusmonitor.com/). Indem Accounts mit anderen sozialen Netzwerken und öffentlich verfügbaren Datenquellen abgeglichen werden, können Dritte außerdem [extrem detaillierte Profile erstellen](https://doi.org/10.1145/2994459.2994471). Aus kommerzieller Perspektive kann solches Wissen für gezielte Werbung oder [Betrugsmaschen](https://www.usenix.org/conference/usenixsecurity19/presentation/tu) genutzt werden. Kriminelle könnten solche Informationen weiterhin für Diskriminierung, Erpressung oder zur Planung eines Verbrechens missbrauchen, wohingegen Nationalstaaten daran interessiert sein könnten, [Bürger zu überwachen oder zu verfolgen](https://www.zdnet.com/article/hong-kong-protesters-warn-of-telegram-feature-that-can-disclose-their-identities/).

Allein die Tatsache, dass eine Telefonnummer bei einem bestimmten Messenger registriert ist kann eine sensible Information sein, speziell wenn diese Nummer einer Person zugeordnet werden kann. Beispielsweise können in Regionen wo manche Dienste strikt verboten sind so ungehorsame Bürger identifiziert und verfolgt werden. Umfangreiche Datenbanken von Telefonnummern, die bei einem bestimmten Dienst registriert sind, erlauben Angreifern, Schaden in großem Stil anzurichten, beispielsweise indem [kompromittierte Nachrichten zur Ausnutzung von Sicherheitslücken in Messengern verteilt werden](https://www.forbes.com/sites/zakdoffman/2019/11/16/new-whatsapp-threat-confirmed-android-and-ios-users-at-risk-from-malicious-video-files/).

Da es für mobile Messenger keine nennenswerten Beschränkungen bei der Registrierung gibt, kann jede dritte Partei eine große Anzahl an Konten erstellen, um sensible Informationen aus der Nutzerdatenbank eines Messengers zu extrahieren, indem Daten für zufällig ausgewählte Telefonnummern abgefragt werden. Solche "Crawling" Angriffe können nicht vollständig verhindert werden, da legitime Nutzer\*innen in der Lage sein müssen, die Datenbank für ihre Kontakte abzufragen. In der Praxis ist sogenanntes "Rate Limiting" eine fest etablierte Maßnahme, um solche Angriffe in großem Stil effektiv einzugrenzen und man würde erwarten, dass Dienstanbieter die Anzahl der erlaubten Anfragen zum Schutz ihrer Plattformen angemessen begrenzen.

### Unsere Beiträge zu **Privatsphäre-schützender** Mobiler Kontaktermittlung

In einer Reihe von wissenschaftlichen Arbeiten demonstrieren wir die Schwere der zuvor beschriebenen Bedrohungen für die Privatsphäre in derzeit verwendeten Verfahren zur mobilen Kontaktermittlung. Darüber hinaus schlagen wir geeignete Gegenmaßnahmen vor, um Angriffe effektiv einzudämmen und entwickeln effiziente kryptographische Protokolle zur Privatsphäre-schützenden mobilen Kontaktermittlung, die so wenige Informationen wie möglich preisgeben.

## Wie WhatsApp, Signal & Co die Privatsphäre gefährden [HWSDS21]

Unsere Studie dreier populärer mobiler Messenger (WhatsApp, Signal und Telegram) zeigt, dass entgegen aller Erwartungen sogenannte Crawling Angriffe in großem Stil möglich sind. Mittels einer akkuraten Datenbank von Präfixen für Mobilfunknummern und sehr wenigen Ressourcen ist es uns gelungen, 10% aller US Mobilfunknummern für WhatsApp und 100% für Signal abzufragen. Bezüglich Telegram zeigt sich, dass dessen API eine Reihe sensitiver Informationen preisgibt, [selbst über Telefonnummern die nicht bei dem Dienst registriert sind](https://core.telegram.org/tdlib/docs/classtd_1_1td__api_1_1imported_contacts.html).

Wir präsentieren interessante Nutzungsstatistiken, die nebenbei zeigen, dass sehr wenige Nutzer\*innen die standardmäßigen Privatsphäre-Einstellungen ändern (die in den meisten Fällen nicht sonderlich Privatsphäre-freundlich sind). Bezüglich Schutzmaßnahmen schlagen wir neue Techniken vor, welche die Durchführbarkeit unserer Angriffe signifikant einschränken, insbesondere ein neues inkrementelles Verfahren zur Kontaktermittlung, das eine strikte Verbesserung gegenüber dem derzeit von Signal verfolgten Ansatz darstellt.

Weiterhin zeigen wir, dass derzeit verwendete Verfahren zur Kontaktermittlung basierend auf Hashing vollständig gebrochen sind, indem wir drei Methoden zum effizienten Umkehren von Hashwerten für Mobilfunknummern vergleichen. Dafür nutzen wir auch eine signifikant verbesserte Konstruktion für sogenannte Rainbow Tables, die spezialisiert ist auf nicht-uniform verteilte Eingaben und sicherlich von unabhängigem Interesse ist. Alle unsere Methoden können Hashwerte von Mobilfunknummern innerhalb von Millisekunden umkehren.

### Responsible Disclosure

Wir demonstrieren Methoden, die es unter dem Einsatz sehr weniger Ressourcen ermöglichen, in die Privatsphäre von Milliarden von Nutzer\*innen von mobilen Messengern einzudringen. Wir haben daher den offiziellen "Responsible Disclosure" Prozess mit allen untersuchten Messengern (WhatsApp, Signal und Telegram) durchlaufen und unsere Erkenntnisse geteilt, um die Ausnutzung durch bösartige Nachahmer zu verhindern.
WhatsApp hat daraufhin seine Schutzmaßnahmen verbessert, um großflächige Angriffe erkennen zu können und Signal hat die Anzahl der möglichen Anfragen reduziert, um Crawling zu erschweren.
 Telegram gab als Antwort auf unsere Offenlegung an, dass bereits zusätzliche Gegenmaßnahmen existieren, die über die von uns erkannten Beschränkungen hinausgehen. Diese werden angeblich ausgelöst, wenn Angreifer Datenbanken von aktiven Telefonnummern nutzen und damit höhere Trefferraten erzielen.

## Effiziente Privatsphäre-schützende Schnittmengenberechnung für Mobile Kontaktermittlung [KRSSW19]

Der derzeit vielversprechenste Ansatz für Privatsphäre-schützende mobile Kontaktermittlung ohne Nutzung sicherer Hardware basiert auf kryptographischen Protokollen zur privaten Schnittmengenberechnung (im Englischen "Private Set Intersection", abgekürzt "PSI"). Solche Protokolle erlauben es Nutzer\*innen und Dienstanbietern, gemeinsame Kontakte zu ermitteln, ohne dass Informationen über sonstige Einträge in den Adressbüchern der Nutzer\*innen sowie den Datenbanken der Dienstanbieter preisgeben werden.

Leider haben sich bisherige Protokolle und Implementierungen selbst in einem schwachen Sicherheitsmodell, bei dem man annimmt, dass Nutzer\*innen nicht von der Protokollspezifikation abweichen, als unpraktikabel für den großflächigen Einsatz herausgestellt. Grund dafür ist die hohe Berechnungs- und/oder Kommunikationskomplexität solcher Protokolle, sowie mangelnde Optimierung der Implementierungen für Mobilgeräte.

Mit unserer Arbeit beseitigen wir die meisten Hindernisse für den weltweiten Einsatz, indem wir zwei vielversprechende Protokolle von [Kiss et al. (PoPETS'17)](https://eprint.iacr.org/2017/670) signifikant verbessern und dabei auch gegen bösartige Nutzer\*innen absichern sowie für Mobilgeräte optimieren. Unser schnellstes Protokoll überprüft 1000 Kontakte in einer großen Datenbank mit 250 Million Einträgen in nur 2.92s, gemessen auf einem Smartphone mit echter WiFi Verbindung und in 6.53s über LTE.

Wir beschreiben die adressierten Privatsphäre-Probleme im Zusammenhang von mobiler Kontaktermittlung und erklären Details über unsere PSI Protokolle in einem leicht verständlichen sowie illustrativen Video auf [YouTube](https://www.youtube.com/watch?v=4vgKHmNaAAw).

## Publikationen
 * [HWSDS21] **_All the Numbers are US: Large-scale Abuse of Contact Discovery in Mobile Messengers_** von Christoph Hagen (Universität Würzburg), Christian Weinert ([TU Darmstadt](https://encrypto.de/weinert)), Christoph Sendner ([Universität Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/staff0/christoph-sendner/)), Alexandra Dmitrienko ([Universität Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/staff0/alexandra-dmitrienko/)) und Thomas Schneider ([TU Darmstadt](https://encrypto.de/schneider)) in [28. Annual Network and Distributed System Security Symposium (NDSS'21)](https://www.ndss-symposium.org/ndss-2021/). Paper verfügbar als **[pre-print](https://encrypto.de/papers/HWSDS21.pdf)**. Implementation verfügbar auf **[GitHub](https://github.com/contact-discovery)**.
 * [KRSSW19] **_Mobile Private Contact Discovery at Scale_** von Daniel Kales ([TU Graz](https://www.iaik.tugraz.at/person/daniel-kales/)), Christian Rechberger ([TU Graz](https://www.iaik.tugraz.at/person/christian-rechberger/)), Thomas Schneider ([TU Darmstadt](https://www.encrypto.de/schneider)), Matthias Senker ([TU Darmstadt](https://www.encrypto.cs.tu-darmstadt.de/home_page/news_feed/news_details_166274.en.jsp)) und Christian Weinert ([TU Darmstadt](https://www.encrypto.de/weinert)) in [28. USENIX Security Symposium (USENIX Security'19)](https://www.usenix.org/conference/usenixsecurity19). Paper verfügbar auf **[ePrint](https://eprint.iacr.org/2019/517)**. Implementation verfügbar auf **[GitHub](https://github.com/contact-discovery)**.
 