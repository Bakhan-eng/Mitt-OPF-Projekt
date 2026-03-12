# Forumprojekt – Blazor Server

## Projektbeskrivning
Detta projekt är en webbapplikation som fungerar som ett forum där användare kan skapa trådar, skriva meddelanden och interagera med andra användare. Applikationen är utvecklad med **Blazor Server** och använder **ASP.NET Core Identity** för användarhantering samt **Entity Framework Core** för databasinteraktion.

Syftet med projektet är att visa hur man kan bygga en modern webbapplikation med användarhantering, diskussionstrådar och databasintegration.

---

# Huvudfunktioner

## Trådhantering
Forumet är uppbyggt kring trådar där användare kan diskutera olika ämnen.

Funktioner:
- Visa alla trådar i systemet
- Öppna en specifik tråd
- Skapa nya trådar
- Radera trådar (trådägare och administratörer)

---

## Meddelandehantering
Användare kan skriva och hantera meddelanden i trådar.

Funktioner:
- Skicka meddelanden i en tråd
- Svara på andra meddelanden
- Visuell indentering för svar (för att visa konversationsträd)
- Redigera egna meddelanden
- Radera egna meddelanden

Administratörer kan:
- Redigera alla meddelanden
- Radera alla meddelanden
- Se alla meddelanden i systemet

---

# Kontohantering
Projektet använder **ASP.NET Core Identity** för att hantera användare.

Funktioner:
- Registrera konto
- Logga in och logga ut
- Uppdatera profilinformation
- Uppdatera e-postadress
- Uppdatera telefonnummer
- Ändra lösenord

---

# Kontoradering
Systemet erbjuder två metoder för att radera ett konto.

## Snabbradering
- Direkt radering från profilsidan
- Bekräftelsedialog innan kontot tas bort

## Avancerad radering
- En separat sida med extra bekräftelsesteg
- Databastranaktioner används för att säkerställa dataintegritet

När ett konto raderas tas även relaterad data bort, till exempel:
- användarens trådar
- användarens meddelanden

---

# Säkerhet
Projektet innehåller flera säkerhetsfunktioner:
- Rollbaserad åtkomst (Admin / User)
- Bekräftelsedialoger för kritiska operationer
- Lösenordsverifiering för känsliga ändringar
- Databastranaktioner för att undvika inkonsekvent data

---

# Adminkonto för testning
För att testa alla funktioner finns ett administratörskonto.

Informationen finns i:
`Models/RoleInitializer.cs`

Där finns användarnamn och lösenord för admin-kontot.

---

# Användarscenarion

## Inloggning
**Scenario:**  
En användare vill logga in för att använda forumets funktioner.

**Steg:**
1. Navigera till inloggningssidan  
2. Ange e-postadress och lösenord  
3. Klicka på **Logga in**

**Förväntat resultat**
- Användaren omdirigeras till startsidan  
- Felmeddelande visas vid felaktiga uppgifter

---

## Skriva kommentar
**Scenario:**  
En användare vill delta i en diskussion.

**Steg**
1. Logga in  
2. Öppna en tråd  
3. Skriv ett meddelande  
4. Klicka på **Send**

**Förväntat resultat**
- Kommentaren visas direkt i tråden  
- Användarnamn och datum visas tillsammans med kommentaren

---

## Uppdatera profil
**Scenario:**  
En användare vill uppdatera sina uppgifter.

**Steg**
1. Logga in  
2. Gå till **Manage Account**  
3. Redigera profilinformation  
4. Klicka på **Save**

**Förväntat resultat**
- Uppgifterna sparas  
- Ett bekräftelsemeddelande visas

---

# Teknisk plattform
Projektet är byggt med följande teknologier:
- ASP.NET Core 8
- Blazor Server
- Entity Framework Core
- SQLite
- ASP.NET Core Identity
- Bootstrap 5

---

# Starta projektet
För att köra projektet lokalt:

1. Navigera till projektmappen
```powershell
cd BlazorApp