# couples-grocery-list
The ultimate grocery list app

 # ISTRUZIONI PER SETUP di Firebase gratis e infinito: (per me) 
 
  1. Vai su https://console.firebase.google.com, crea un progetto nuovo.
 
  2. Aggiungi l'autenticazione:
     "Authentication" > "Sign-in method" > abilita "Email/Password".
         Poi vai su scheda "Users" > "Add user" e crea DUE utenti:
         (me e davide) (email + password a scelta, anche finte
         tipo martina@listaspesa.local,). Dopo averli creati, copia "User UID" al punto 5.
      
   3. Crea il database: "Database" > "Realtime Database" > "Crea database".
      Scegli "Avvia in modalità blocco" (locked mode).

   4. "Aggiungi app > web app (nome a caso). Copia
      l'oggetto firebaseConfig e incollalo nel codice.
   
   5. Vai su "Realtime Database" > scheda "Rules" e incolla queste regole,
      sostituendo UID_MARTINA e UID_DAVIDE con gli UID copiati al punto 2.
   
      {
         "rules": {
            "lista-spesa": {
            ".read": "auth != null && (auth.uid === 'UID_MARTINA' || auth.uid === 'UID_DAVIDE')",
            ".write": "auth != null && (auth.uid === 'UID_MARTINA' || auth.uid === 'UID_DAVIDE')"
            }
         }
      }
      Clicca "Pubblica".