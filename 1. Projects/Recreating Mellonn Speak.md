# Ideas for recreating Mellonn Speak
- Collaborative transcribing.
- AI helper, to find specific quotes in the transcription.
- Better feedback loop.
- New pricing model.
	- Freemium?
	- Both subscription and pay-as-you-go options?
	- Monthly, quarterly and yearly payment options.
	- Usage based discounts.
	- Payment for having multiple collaborators.
- Highlighting and note taking built in.
- Make a product that is non-AI first and implements AI features, instead of AI first.
	- Non-AI features will be free (1-3 free recordings at a time and deleting one will free up another).
	- Manual transcription will always be free. But having an AI do it will cost money (either pay-as-you-go or subscription).
	- AI for searching and helping with things in the transcription will be on a subscription basis (this could be an argument to make AI-transcription on a subscription too, to make it simpler).

## New target customers?
- B2B as main objective.
	- Still maintaining students as secondary customers. Because students don't wanna pay for anything.
	- The plan is to make money off of businesses to then give students a good product for much less.

### How do we differentiate businesses from students?
- Providing on-prem support for businesses.
- Support for collaboration between everyone or just teams within businesses.
- At a later point support for creating subtitles to videos.
- Easy to setup accounts (SAML support or something).

## Tech Stack
| Purpose | Product | Why? | Link |
| ---- | ---- | ---- | ---- |
| **Web App** | SvelteKit | It's Based | https://kit.svelte.dev/ |
| **Backend Functions** | Go | Fast, reliable and easy to learn. | https://go.dev |
| **Authentication** | WorkOS | Cheap and easy to scale. | https://workos.com |
| **Payments** | Stripe | It's great and good docs. | https://stripe.com/en-dk |
| **Database** | PlanetScale | Cheap and scalable, PostgreSQL | https://planetscale.ccom |
| **Storage** | S3 (of some sort) | Reliable, easy to use and scalable. | Wasabi, Linode, AWS, Backblaze, Storj and Cloudflare. **Scaleway**. |
| **Notifications** |  |  |  |
| **Transcription model** | OpenAI Whisper | Open Source, Huggingface. | https://huggingface.co/openai/whisper-large-v3 |
| **Speaker Diarization** | Pyannote Speaker Diarization | Open Source, Huggingface. | https://huggingface.co/pyannote/speaker-diarization-3.1 |
| **Error handling Frontend** | Sentry | Cheap, easy to implement. | https://sentry.io/welcome/ |
| **Main cloud provider** | Vercel, Scaleway or AWS | Cheap ish and easy. | https://www.scaleway.com/en/ |
| **Logging** | Axiom | Cheap and easy logging. | https://axiom.co/ |
| **Analytics** | Posthog | Cheap alternative to Google Analytics. | https://posthog.com/ |
### Suggestions or thoughts
- Using GRPc to create connection between client and server.
	- https://grpc.io/
- Authentication article with SvelteKit and Go.
	- https://dev.to/sirneij/authentication-system-using-golang-and-sveltekit-dockerization-and-deployments-139h
- Uploadthing.
	- https://docs.uploadthing.com/faq
- WorkOS (Auth).
	- https://workos.com/?gad_source=1
- Shadcn Svelte.
	- https://www.shadcn-svelte.com/
- Axiom for logging.
	- https://axiom.co/
- PlanetScale for Database.
	- https://planetscale.com/pricing
- 
