# TriageFlow

## Om projektet

TriageFlow är ett Python-projekt som simulerar ett digitalt triagesystem.
Användaren får ange information om en patient och patientens symptom.
Målet är att programmet senare ska kunna använda AI för att hjälpa till
att bedöma hur akut ett vårdärende är.

## Syfte

Syftet med projektet är att utveckla mina kunskaper inom Python och
undersöka hur AI kan användas inom digital vård och triage.

## Teknik

- Python
- Git
- GitHub

## Status

Projektet är under utveckling.

## Testing

Manuella tester genomförda:

- [x] Flera patienter kan registreras under samma körning.
- [x] Varje patient får en separat AI-bedömning via API.
- [x] AI-bedömningen sparas i `ai_response` i `patients.csv`.
- [x] Nya patienter läggs till utan att tidigare CSV-data skrivs över.
- [ ] Akutpatient (`pain_scale >= 8`) sparas med `emergency_reason`.

### Upptäckta förbättringsområden

- Programmet tillåter för närvarande att symptombeskrivningen inte matchar vald symptomkategori, exempelvis `"ont i halsen"` under `"Sår/Skador"`. Framtida validering kan kontrollera eller varna för sådana motsägelser.