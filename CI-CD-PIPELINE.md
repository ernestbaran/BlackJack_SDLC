# Pipeline CI/CD - Documentazione Automatica

## 🎯 Obiettivo

Automatizzare la generazione e pubblicazione della documentazione del progetto ogni volta che viene fatto un push su `master`.

---

## 🏗️ Architettura della Pipeline

### Trigger
- **Push** sul branch `master`
- **Workflow dispatch** (esecuzione manuale)

### Environment
- **Runner**: Ubuntu Latest
- **Node.js**: Versione 18

### Steps della Pipeline

1. **Checkout Repository** - Scarica il codice
2. **Setup Node.js** - Installa Node.js v18
3. **Generate Docs** - Genera HTML con JSDoc
4. **Deploy** - Pubblica su GitHub Pages (branch `gh-pages`)

---

## 📁 File di Configurazione

**Percorso**: `.github/workflows/docs.yml`

La pipeline si attiva automaticamente ad ogni push su master e genera la documentazione da commenti JSDoc nel codice.

---

## 🔄 Workflow
```
Developer Push → GitHub → Actions Trigger → Ubuntu VM
                                                ↓
                                    Genera Documentazione
                                                ↓
                                    Deploy su gh-pages
                                                ↓
                        GitHub Pages Aggiorna Automaticamente
```

---

## ✅ Vantaggi

1. **Automazione Totale** - Zero intervento manuale
2. **Documentazione Sempre Aggiornata** - Sincronizzata con il codice
3. **Continuous Integration** - Verifica errori JSDoc
4. **Continuous Deployment** - Pubblicazione automatica

---

## 🌐 Accesso alla Documentazione

**URL Live**: https://ernestbaran.github.io/BlackJack_SDLC/

La documentazione viene aggiornata entro 1-2 minuti da ogni push su `master`.

---

## 🐛 Troubleshooting

### Pipeline Fallisce
- **Errore 128**: Permessi insufficienti → Abilita "Read and write" in Settings → Actions
- **JSDoc Error**: Controlla sintassi commenti nel codice

### Documentazione Non Si Aggiorna
1. Verifica pipeline verde (tab Actions)
2. Controlla GitHub Pages abilitato
3. Aspetta 2-3 minuti
4. Pulisci cache browser (Ctrl+F5)

---

## 📊 Metriche

- **Tempo Build**: ~1-2 minuti
- **Trigger**: Ad ogni push su master
- **Costi**: $0 (GitHub Actions free tier)

---

**Versione**: 1.0  
**Data**: 09/03/2026  
**Stato**: ✅ Attiva