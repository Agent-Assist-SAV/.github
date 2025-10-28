# Agent Assist SAV — WhatsApp & co (frontend)

Prototype d’assistant de réponse pour équipes SAV. Il propose des suggestions courtes en temps réel, générées côté serveur et diffusées en streaming vers l’interface opérateur.

## Pour qui

- SAV/Support de marques e‑commerce, retail, services.
- Plateformes relation client souhaitant un “copilot” prêt à intégrer.

## Ce que le produit apporte

- Gain de temps: suggestions de réponses prêtes à être envoyée.

## Composants produit

- Interface opérateur: SPA React/TypeScript.
- Moteur d’assistance: API FastAPI qui génère des suggestions et les stream en SSE. Les suggestions sont générées par IA grace à un model déployé sur le cloud (OVH).

## Fonctionnement (en bref)

1) Ajout de contexte par l'agent.
2) Ouverture d'une discussion. En mode "développement", simulation d'un envoi d’un message utilisateur
3) Réception du nouveau message côté serveur, puis génération de la suggestion de réponse et diffusion de la suggestion en streaming (SSE)  
4) Validation/édition par l’agent avant envoi du message de réponse au client.

## Tech stack

### Frontend
- React 18 + TypeScript — frontend framework  
- Vite — build tool & dev server  
- Tailwind CSS + shadcn/ui — styling & components  
- React Router — routing SPA  
- React Hook Form + Zod — formulaires & validation  
- TanStack Query — requêtes & cache  
- Radix UI — primitives composants  
- Sonner, Recharts, Lucide — toast, graphiques, icônes  
- ESLint + TypeScript — code quality

### Backend
- FastAPI + Starlette + Uvicorn
- Streaming Server-Sent Events (SSE) pour les suggestions
- Provider LLM: intégration OVHcloud AI
- CORS ouvert vers l’app front en développement
