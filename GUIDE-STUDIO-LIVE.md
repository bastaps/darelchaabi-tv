# STUDIO LIVE CHAABI TV - Guide artiste

## 🎯 Ce que tu as maintenant

Tu as 2 sites interconnectés :
1. **chaabi-tv-complete.html** = vitrine publique + lecteur YouTube
2. **studio-live-chaabi.html** = ton studio télé privé (celui que tu viens d'ouvrir)

Depuis le studio, tu peux :
- Chanter devant ta webcam → décor virtuel Chaabi automatique derrière toi (IA détourage)
- Diffuser EN MÊME TEMPS sur YouTube + Facebook + TikTok + Instagram depuis ton site
- Enregistrer en local et créer ta chaîne télé YouTube 24/7

---

## 🏛️ Les 5 décors virtuels inclus (dans /assets/decors/)

1. **Casbah Chaabi** - salon traditionnel algérois, mandoles, tapis, lanternes (authentique)
2. **Studio TV Moderne** - plateau télé pro avec lumières dorées, fond noir/or (recommandé pour chant)
3. **Salon Andalou Luxe** - palais, zellige, arches, ambiance palace
4. **Scène Opéra Concert** - grande scène avec rideaux rouges, projecteurs (pour concerts)
5. **Fond Gold Chaabi** - abstrait luxe bleu nuit + arabesques dorées + silhouette mandole (minimal, élégant)

Tu peux importer tes propres décors : bouton "+ Importer" → choisis une image 16:9.

**Comment ça marche le décor virtuel ?**
- Le site utilise MediaPipe Selfie Segmentation (IA Google) qui découpe ta silhouette en temps réel
- Il remplace l'arrière-plan par l'image choisie
- Astuce pro : éclairage de face + fond uni (mur clair) = détourage parfait. Pas besoin de fond vert.

---

## 🔴 Comment faire un DIRECT MULTI depuis ton site (YouTube + FB + TikTok + IG)

### Le problème
Un navigateur ne peut pas pousser 4 flux RTMP directement. Instagram et TikTok bloquent le RTMP direct.

### La solution pro (2 minutes, gratuite)
On passe par **Restream.io** qui fait relais : 1 flux depuis ton site → Restream → redistribue vers les 4 plateformes.

**Étapes :**
1. Va sur https://restream.io → crée compte gratuit
2. Dans Restream, clique "Add Channel" → connecte :
   - YouTube (autorise)
   - Facebook Page (autorise)
   - TikTok (si tu as 1000 abonnés + accès Live, sinon Custom RTMP)
   - Instagram (via plugin Restream, ou YellowDuck)
3. Restream te donne UNE SEULE clé : `rtmp://live.restream.io/live` + `re_XXXXXX`
4. Dans ton studio (studio-live-chaabi.html), colle cette clé dans le champ **"RTMP Restream - 1 clé = 4 plateformes"**
5. Clique **"Activer caméra"** → choisis décor → **"GO LIVE MULTI"**
6. Tu es en direct partout ! Le badge LIVE s'allume, le chat agrégé affiche les commentaires YT/FB/TT/IG en même temps.

**Alternative 100% pro avec OBS :**
- Bouton "Copier config OBS" dans le studio → colle dans OBS Studio → Source Navigateur = ton site studio → OBS Virtual Camera → Restream.
- Avantage : qualité 1080p60, plusieurs caméras, transitions.

### Où trouver tes clés RTMP ?
- **YouTube** : YouTube Studio → Créer → Diffuser en direct → Clé de diffusion → Copier
- **Facebook** : Meta Business Suite → Outils de diffusion → Clé RTMP persistante
- **TikTok** : TikTok Live Center (sur PC) → si éligible, clé RTMP. Sinon passe par Restream Custom RTMP.
- **Instagram** : pas de RTMP natif. Restream a un plugin Instagram qui te connecte.

---

## 📺 Comment créer une chaîne télé YouTube depuis ton site

Tu veux que ta chaîne tourne en direct 24/7 même quand tu dors (boucle de tes vidéos Chaabi) ?

1. Dans le studio, bouton **"🔁 Mode boucle 24/7"**
2. Dans Restream, active **"Live Loop"** ou **"Pre-recorded"** → upload tes 12 vidéos tests
3. Sur YouTube, programme un Live 24/7 "Dar El Chaabi TV - Non Stop"
4. Résultat : YouTube affiche "EN DIRECT" en permanence avec tes replays, tu peux couper pour faire un vrai live chant à tout moment.

C'est comme une vraie chaîne télé.

---

## 🎙️ Workflow artiste recommandé

**Avant le live (5 min) :**
- Ouvre studio-live-chaabi.html
- Activer caméra → choisir décor "Studio TV Moderne" ou "Casbah"
- Choisir mise en scène : Plein écran (chant) ou Cadre TV (interview)
- Renseigner nom artiste + titre chanson → bandeau bas s'affiche auto
- Coller paroles dans téléprompteur → bouton Éditer
- Tester connexions RTMP

**Pendant le live :**
- GO LIVE MULTI → REC local démarre auto
- Chante, lis le téléprompteur qui défile
- Réponds au chat multi-plateformes en bas
- Change de décor en 1 clic pendant le live (effet TV)

**Après le live :**
- STOP LIVE → Télécharger enregistrement → bouton "Télécharger dernier enregistrement"
- L'enregistrement est déjà avec décor + bandeau + logo → prêt à uploader en Replay YouTube
- Il est aussi découpable en 5-10 Shorts (déjà prévu dans le site principal)

---

## 🛠️ Fichiers

- `studio-live-chaabi.html` → ton studio (à garder privé ou protégé par mot de passe)
- `assets/decors/*.jpg` → 5 décors générés, remplaçables
- `chaabi-tv-complete.html` → site public avec lien vers studio

Héberge les deux sur le même domaine. Mets un mot de passe sur le studio si tu veux (via Netlify _headers ou Vercel protection).

Besoin que je :
- Génère d'autres décors (ex: studio avec orchestre, fond vert, etc.) ?
- Ajoute un prompteur karaoké avec paroles qui surlignent ?
- Connecte tes vraies clés Restream/YouTube maintenant ?
