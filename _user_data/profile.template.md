# Team Profile Template

Copy this file to `_user_data/profile.md` during onboarding. The real `profile.md` file is ignored by Git because it can contain team names, phone numbers, source systems, and escalation contacts.

The orchestrator triggers `start onboarding` every new chat until `_user_data/profile.md` exists and is populated.

## What this file will contain after onboarding

After you run `start onboarding`, the assistant interviews you, then gives you a completed `profile.md` to save here. The structure is the same as the template below. You do not edit this template manually.

```
# Team Profile

## Agent (primary)
- Name:
- Brokerage:
- License number:
- MLS Member ID:
- Primary phone:
- Email:

## Team members
- Name, role, license status (if any)
- Name, role, license status

## Markets covered
- Primary metro:
- ZIP codes:
- Neighborhoods:
- Typical price range:

## MLS
- Name:
- Coverage area:
- Source-checked-at default: today's date

## Source systems (where the deal lives)
- CRM:
- Email:
- Document storage:
- Transaction management:
- Calendar:

## Voice and style
- Default tone (one sentence):
- Email length default:
- Text length default:
- Greeting style:
- Sign-off style:
- Phrases I always use:
- Phrases I never use:

## Escalation owners
- Broker:
- Attorney (preferred):
- Lender (preferred):
- Title company (preferred):
- Inspector (preferred):

## Compliance preferences
- Languages we serve (English only / bilingual / etc.):
- Compliance review threshold:

## Last updated
- Date:
```

## See it filled in

For a complete worked example showing what a finished profile looks like, see [`profile.example.md`](profile.example.md) in this folder. That is a synthetic Diana profile, not real team data.

## How to replace this file

When the orchestrator finishes onboarding, it will:

1. Show you the completed profile as a downloadable `profile.md` file in chat.
2. Tell you to drag the downloaded file into your project's knowledge area.
3. Tell you to save the populated output as `_user_data/profile.md`.

You do not need to read or understand the template above. The assistant handles it.
