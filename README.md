# TriageFlow

## Om projektet

TriageFlow är ett Python-projekt som simulerar ett digitalt triagesystem.
Användaren får ange information om en patient och patientens symptom.
Målet är att programmet senare ska kunna använda AI för att hjälpa till
att bedöma hur akut ett vårdärende är.

## Mål och Syfte

Syftet med projektet är att utveckla mina kunskaper inom Python och
undersöka hur AI kan användas inom digital vård och triage.

## Metod och Teknik

- Python
- Git
- GitHub

## Resultat

## Branchanalys

## Relevanta certifikat

## Reflektion

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