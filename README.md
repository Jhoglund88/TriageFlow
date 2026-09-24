# TriageFlow

## Om projektet

TriageFlow är ett Python-projekt som simulerar ett digitalt triagesystem. Användaren får ange information om en patient och dennes symptom. Därefter skickas användarens input till en språkmodell via Groq API som gör en bedömning och återkommer med rekommendationer. Registrerade uppgifter sparas tillsammans med AI-svaret i en lokal CSV-fil.

Projektet använder endast påhittade patientuppgifter för testning och efterfrågar inte namn, peronnr eller kontaktuppgifter. Ålder och symptombeskrivningar kan ändå identifiera en person i vissa sammanhang, och fritextfälten blockerar inte personuppgifter. Verkliga patientuppgifter ska därför inte matas in.

## Mål och Syfte

Syftet med projektet är att utveckla mina kunskaper inom Python och
undersöka hur AI kan användas inom digital vård och triage.

Målet är att skapa ett enkelt traigesystem där användaren får mata in fiktiva uppgifter och symptom för att sedan kunna få en bedömning från AI.

## Metod och Teknik

Programmet är utvecklat i Python och använder objektorienterad programmering med klasser och arv för att representera olika typer av patienter.

Tekniker och verktyg som används:

- Python - Programmets huvudspråk.
- Groq API - för kommunikation med språkmodellen: openai/gpt-oss-120b.
- Requests - används för att göra API-anrop
- CSV - för att spara patientuppgifter samt AI-svar lokalt.
- Pandas - används för att läsa och visualisera data i diagram
- Matplotlib - används för att visualisera data i diagram
- python-dotenv - används för säker hantering av API-nyckeln via en .env-fil
- Git och Github - används för versionshantering och projektets utvecklingsflöde.


## Resultat

## Branchanalys

Inom vården använder man AI alltmer för att analysera information, effektivisera arbete och ge stöd vid olika typer av bedömningar. Detta projekt är ett exmpel på hur AI kan användas för att ta emot patientinformation och sen ge rekommendationer utifrån den angivna informationen. I Triageflow tex. sker detta genom att informationen skickas via ett API till en språkmodell som analyserar informationen och genererar ett svar.

Det är samtidigt viktigt att vara medveten om att AI kan ge felaktiga eller missvisande svar och därför inte bör användas som underlag vid medicinska bedömningar.

## Relevanta certifikat

För en AI-utvecklare finns flera relevanta certifieringar. Exempel på några som passar till TriageFLow är:

- **Microsoft Certified: Azure AI Apps and Agents Developer Associate (AI-103)**
Inriktad på utveckling av AI-applikationer och generativ AI.
- **AWS Certified AI Practitioner**
Ger grundläggande kunskaper inom AI och generativ AI.
- **AWS Certified Machine Learning Engineer-Associate**
Mer inriktad på utveckling och driftsättning av AI- och ML-lösningar i molnet.

Certifieringarna är relevanta för Triageflow eftersom projektet kombinerar Python med generativ AI och extern AI-tjänst. Det sistnämnda certifikatet är användbart om man skulle vilja vidareutveckla TriageFlow och göra det mer användbart i praktiken.

## Reflektion

Under projektets har jag lärt mig väldigt mycket, inte bara om själva Python-språket utan även om hur viktigt det är med planering och struktur. Jag har flera gånger fått tänka om och ändra delar av programmet på grund av problem som uppstått.

Några problem som uppstod är:

- **API-integrationen** 
För att undvika att visa api-nyckeln i själva koden eller råka skicka med den till GitHub lade jag den i en .env-fil (som behöver vara med i .gitignore för att ej följa med till Git). Jag behövde undersöka hur JSON-svaret var strukturerat för att kunna plocka ut rätt information.

- **Spara AI-svaret i CSV-filen**
AI-svaret skapades först efter att patientobjektet redan hade skapats. För att lösa detta lade jag till ai_response som ett attribut på Patient-klassen. Detta med ett tomt standardvärde för att AI-svaret ännu inte finns när Patient-objektet skapas. När API-amropet sedan har gjorts sparas resultatet i patient.ai_response. Därefter behövde jag uppdatera funktionen save_patients() så att även AI-svaret skrivs till CSV-filen på rätt ställe.

-**Integritet/GDPR**
När programmet i princip var färdigställt insåg jag att det finns risk att användaren skriver in känsliga uppgifter och lade därför till en integritetsvarning som uppmanar användaren att endast använda fiktiva uppgifter. Programmet informerar även om att det är skapat i utbildningssyfte och inte ska användas för medicinsk rådgivning.

Jag tycker att valet att använda ett API till en språkmodell fungerade bra för projektets syfte eftersom jag kunde integrera generativ AI kan  utan att själv utveckla eller träna en AI-modell. Jag valde att spara informationen i en CSV-fil då detta var tillräckligt för mitt projekt men om projektet ska utvidgas kan och bli mycket större hade en databas varit lämplig. Projeketet visar hur man kan använda generativ AI i vanliga applikationer men också risker samt begränsningar (felaktiga svar och hantering av känsliga uppgifter).

## Github-länk

## Installation och körning

## Ai-användning

## Tester

Manuella tester genomförda:

- [x] Flera patienter kan registreras under samma körning.
- [x] Varje patient får en separat AI-bedömning via API.
- [x] AI-bedömningen sparas i `ai_response` i `patients.csv`.
- [x] Nya patienter läggs till utan att tidigare CSV-data skrivs över.
- [x] Akutpatient (`pain_scale >= 8`) sparas med `emergency_reason`.
- [x] Patientdata sparas även om AI-bedömningen misslyckas.
- [x] Saknad API-nyckel hanteras utan att programmet kraschar.
- [x] Felaktig API-nyckel hanteras som ett HTTP-fel.
- [x] Timeout vid API-anrop hanteras utan att programmet kraschar.
- [x] Ogiltigt JSON-svar hanteras utan att programmet kraschar.
- [x] API-svar med oväntat format hanteras utan att programmet kraschar.

## Status och begränsningar

Projektet är under utveckling.