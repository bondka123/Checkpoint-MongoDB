# 📁 MongoDB CRUD Project - GOMYCODE Checkpoint

## 📌 Objectif

L'objectif de ce projet est de pratiquer les opérations CRUD (Create, Read, Update, Delete) en utilisant MongoDB via le Shell (`mongosh`).

---

## 📂 Base de données utilisée

- **Nom de la base** : `contact`
- **Nom de la collection** : `contactlist`

---

## ✅ Étapes réalisées
2. Insertion des documents
db.contactlist.insertMany([
  { nom: "Ben", prenom: "Moris", email: "ben@gmail.com", age: 26 },
  { nom: "Kefi", prenom: "Seif", email: "kefi@gmail.com", age: 15 },
  { nom: "Emilie", prenom: "brouge", email: "emilie.b@gmail.com", age: 40 },
  { nom: "Alex", prenom: "brown", age: 4 },
  { nom: "Denzel", prenom: "Washington", age: 3 }
])

3. Lire toutes les données (afficher tous les contacts)
db.contactlist.find().pretty()

4. Lire un contact par son _id
db.contactlist.findOne({ _id: ObjectId("REMPLACEZ_PAR_L_ID") })

5. Lire tous les contacts avec age > 18
db.contactlist.find({ age: { $gt: 18 } })

6. Lire les contacts avec age > 18 et nom contient "ah"
db.contactlist.find({
  age: { $gt: 18 },
  nom: { $regex: "ah", $options: "i" }
})

7. Mise à jour du prénom de "Kefi Seif" en "Kefi Anis"
db.contactlist.updateOne(
  { nom: "Kefi", prenom: "Seif" },
  { $set: { prenom: "Anis" } }
)

8. Suppression des contacts ayant age < 5
db.contactlist.deleteMany({ age: { $lt: 5 } })

9. Affichage final de tous les contacts
db.contactlist.find()
