---
title: Fyrverkerier
level: Nivå 1
language: sv-SE
stylesheet: scratch
embeds: "*.png"
note: "till_instruktorerna.md"
...

# Introduktion {.intro}

I det här projektet ska vi skapa ett fyrverkeri över en stad. 

#STEG 1: Skapa en raket som flyger mot muspekaren {.activity}

__Låt oss importera olika bilder för spelet__

##Checklista {.check}

+ Starta ett nytt Scratchprojekt. Radera katten genom att högerklicka på den och välj Radera. Döp projektet till "Fyrverkerier".
+ Gå till Scenen och importera bakgrunden Utomhus/city-with-water. Ta bort den tomma bakgrunden.
+ Importera en raketsprajt från biblioteket <img alt="" class="inline" src="int-library.png">. Välj Saker/Candle som mest liknar en raket av alla bilder. Döp sprajten till Raket.
+ Se till att ljuset är vänt upp-och-ner när vi startar och att den är gömd.

```blocks
när @ klickas på
peka i (-90 v) riktning
göm
```

Nu vill vi att raketen ska röra sig mot muspekaren när musen har klickats. 

+ Lägg till ett nytt skript som visar raketen och låter den glida till muspekaren när vi trycker på mellanslag.

```blocks
när @ klickas på
peka i (-90 v) riktning
göm

när [space v] trycks
visa
glid (1) sek till x:(mus x) y:(mus y)
```
	
##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, placera muspekaren över scenen och tryck på mellanslag.__

+ Visas raketen och rör den sig mot musen?
+ Vad händer om du rör musen och slår mellanslag igen?

##Checklista {.check}

+ Fyrverkerier brukar inte flyga från sida till sida, så låt oss se till att den alltid glider mot musen från botten av skärmen. Innan vi visar raketen, använd `gå till` {.blockmotion}-blocket för att säga åt den att röra sig från botten av skärmen, men inte röra sig åt sidorna. 

```blocks
när @ klickas på
peka i (-90 v) riktning
göm

när [space v] trycks
gå till x:(mus x) y:(-200)
visa
glid (1) sek till x:(mus x) y:(mus y)
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, placera musen över scenen och tryck på mellanslag.__
+ Flyger raketen mot musen från botten av skärmen? 
+ Vad händer om du rör musen och trycker mellanslag igen?

##Checklista {.check}

Slutligen, låt oss få detta att fungera genom att använda musknappen istället för mellanslag. 
+ Ersätt `när mellanslag trycks ned` {.blockevents} med två block: `för alltid` {.blockcontrol} och `om ... då` {.blockcontrol} med ett `musknappen nedtryckt` {.blocksensing}-block i.

```blocks
för alltid
    om <musknappen nedtryckt?> då
        gå till x:(mus x) y:(-200)
        visa
        glid (1) sek till x:(mus x) y:(mus y)
    end
end
```

+ Lägg ihop de två blocken du har så de blir ett enda: 

```blocks
när @ klickas på
peka i (-90 v) riktning
göm
för alltid
    om <musknappen nedtryckt?> då
        gå till x:(mus x) y:(-200)
        visa
        glid (1) sek till x:(mus x) y:(mus y)
    end
end
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan, tryck sedan på musknappen någonstans på scenen. Klicka igen på en annan punkt.__ 

##Saker att pröva {.try}
+ Försök att göra några raketer lite långsammare eller snabbare än andra. 
+ Försök att ändra raketens riktning innan den glider mot muspekaren så att den får en båge. 

##Spara ditt projekt. {.save}

#STEG 2: Gör så att raketen exploderar {.activity}

##Checklista {.check}

+ Första steget för att få raketen att explodera är att se till att det spelas ett bang-ljud (Effekter/chomp) innan den börjar röra på sig, och sedan gömma sig då den når musen. För att importera ett ljud, gå till Ljud-fliken och klicka på import.

```blocks
när @ klickas på
peka i (-90 v) riktning
göm
för alltid
    om <musknappen nedtryckt?> då
        gå till x:(mus x) y:(-200)
        spela ljudet [chomp v]
        visa
        glid (1) sek till x:(mus x) y:(mus y)
		göm
    end
end
```
Nu ska vi göra så att raketen sänder ett nytt meddelande när den exploderar. Vi kommer att lyssna efter detta meddelande senare.
+ Dra ut ett `skicka` {.blockevents}-block och välj "nytt meddelande" och skriv in "explosion". Lägg in det i skriptet så här:

```blocks
när @ klickas på
peka i (-90 v) riktning
göm
för alltid
    om <musknappen nedtryckt?> då
        gå till x:(mus x) y:(-200)
        spela ljudet [chomp v]
        visa
        glid (1) sek till x:(mus x) y:(mus y)
        göm
        skicka [explosion v]
    end
```

##Testa ditt projekt {.flag}

__Klicka på den gröna flaggan.__ 
+ Se till att raketen spelar ett ljud och göms när den når musen. 

##Checklista {.check}

+ Skapa en ny sprite från fil. Tryck på `Ladda upp sprajt från fil` och lägg in följande länk i rutan Filnamn: http://www.zenlan.com/learn/scratch/resources/Fireworks/firework1.png
Om inte det fungerar kan du rita en fyrverkerisprajt eller importera något liknande, t.ex. Saker/beachball
+ Ändra namn på den nya sprajten till "fyrverkeri".
4. När den tar emot explosionsmeddelandet ska den gömma sig och sedan flyttas till raketens position genom att använda `gå till` {.blockmotion}-blocket, för att sedan försvinna igen en sekund senare.

```blocks
när jag tar emot [explosion v]
göm
gå till x:([x position v] av [Raket v]) y:([y position v] av [Raket v])
visa
vänta (1) sekunder
göm
```
##Testa ditt projekt {.flag}
__Skicka en annan flygande raket.__ 
+ Blir den ersatt med en explosionsbild när den exploderar? 
+ Vad händer om du håller musknappen nere medan du rör på musen? (Oroa dig inte, vi ska fixa det här senare).

##Spara ditt projekt {.save}

#STEG 3: Gör varje explosion unik {.activity}

+ Nu kan vi göra varje explosion mer unik genom att använda `sätt färg effekten` {.blocklooks}-blocket, och låta det välja slumpmässiga färger mellan 1 och 200 innan det visas.

```blocks
när jag tar emot [explosion v]
göm
sätt [color v] effekten till (slumptal (1) till (200))
gå till x:([x position v] av [Raket v]) y:([y position v] av [Raket v])
visa
vänta (1) sekunder
göm
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

Har varje explosion olika färg?

+ Du kan lägga till fler explosionsbilder genom att leta på bilder på internet och spara dem på din dator och sedan gå till fliken `Klädslar` på explosionssprajten och importera nya klädslar från fil. Sen kan du byta mellan dem med `nästa klädsel` {.blocklooks}-blocket innan de visas.

##Checklista {.check}

+ Slutligen, låt oss göra så att explosionen blir större efter att raketen exploderar! Istället för att vänta en sekund, sätt storleken på spriten till 5% innan den visas. Och sedan när den visas öka storleken med 2 femtio gånger genom att använda ett repetitionsblock. 

```blocks
när jag tar emot [explosion v]
göm
sätt [color v] effekten till (slumptal (1) till (200))
gå till x:([x position v] av [Raket v]) y:([y position v] av [Raket v])
sätt storleken till (100)%
visa
repetera (50)
    ändra storlek med (2)
end
göm
```

##Testa ditt projekt {.flag}
__Klicka på den gröna flaggan.__ 

+ Sprider sig explosionsbilden från mitten av raketen och växer sakta? 

##Saker att pröva {.try}
Varför inte försöka göra varje explosion unik genom att ändra storlek och förstoringshastighet?

##Spara ditt projekt {.save}

__Bra gjort du är klar, nu kan du njuta av spelet!__

Glöm inte att du kan dela ditt spel med alla dina vänner och din familj genom att klicka på "Dela ut" på menyn!

