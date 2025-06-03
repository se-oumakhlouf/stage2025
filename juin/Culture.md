- **Admin** : 
	- Double PC :  Bureautique / Admin

- Mot de Passe :
	- Reset obligatoire tous les 6 mois
	- 15 caractères minimum -> majuscules, minuscules, chiffres, caractères spéciaux

- **Spring Batch :**
	- Renvoie les utilisateurs dont le `last update` du mot de passe date d'il y a 5 mois (temps restant pour changement de mot de passe : `< 1 mois`)
	- Envoie un mail de notif à ces utilisateurs (compte bureautique) comprenant un lien (`api/uuid`) pour changement de mot de passe
	- ⬆️Remplacer `@` par `.` pour recherche dans la base de données

- **Changement de mot de passe :**
	- Envoie d'un code à 6 (ou 8) chiffres par mail
	- Formulaire :
		- `old password`
		- `new password`
		- `new password`
		- `code à 6 (ou 8) chiffres`
	- Vérification du délai entre envoie du code et réponse au formulaire (~15 min)
	- Enregistrement du nouveau mot de passe (dans la deuxième BDD ?)
	- Mise à jour de `last update` dans la BDD


- Users :
	- long id
	- string email
	- LocalDateTime lastReset

- Passwords :
	- long id
	- long userId
	- long passwordHash
	- LDT changedAt

- Tokens :
	- long id
	- long userId
	- string tokenValue (uuid)
	- LDT expirationTime
	- Status {Active, Inactive, Expired}