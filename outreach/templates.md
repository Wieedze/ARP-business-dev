# Outreach templates

All outgoing messages are in English unless the contact is French (then write in French, same structure). Every message is created as a **Gmail draft** for Maxime to review and send. Fill every `{placeholder}`; if a placeholder cannot be filled from the pipeline or the repo, leave the draft out and list the gap in the weekly recap instead.

Signature on every message: `Maxime` (no title, no links unless the template asks).

## T1. Intro request to a connector

Use when `channel = intro` and the connector is a person Maxime knows.

> Subject: Intro to {investor or person}? (ARP)
>
> Hi {connector first name},
>
> Would you be open to asking {investor} if they'd take a 20 min call with me? A short blurb you can forward as is is below. No pressure if it's not a fit.
>
> Maxime
>
> ---
>
> Maxime (co-founder of Sofia, Intuition grantee) is building ARP, which makes money flow to the tools AI agents actually use. Agents record each tool call that works on an open graph anyone can verify. {One traction line from the latest numbers.} He's not raising yet and would value {investor}'s view on {topic from the pipeline "why" column}.

## T2. First contact to an agent operator (users)

Use for `kind = user` operators (centralcity.ai, Olas operators).

> Subject: Free usage badge for your agents on Base
>
> Hi {name or team},
>
> I measure the ERC-8004 registry on Base, and your agents make up a large part of it ({specific figure from notes}). I'm building ARP: agents record which tools they actually use, on Intuition's open graph, and get a public "used by N agents" badge.
>
> I'd like to import your agents for free and set up the hook with you, 15 minutes. Interested?
>
> Maxime

## T3. GitHub issue to a tool author (originals vs copies)

Prepared as a text file in `outreach/drafts/`, not posted. Maxime posts it.

> Title: Your skill is being republished under other names; free page showing the original
>
> Hi {author}, I measured skills.sh install counts on {date}: {n} repositories publish byte-identical copies of {skill}, and {m} of them out-install the original. I built a page on ARP that shows the original next to its copies, with real usage by agents rather than installs. Happy to add a badge to your README if useful. No strings attached.

## T4. Follow-up at 7 days, no reply

> Subject: Re: {original subject}
>
> Hi {first name}, a quick bump on this in case it got buried. {One new fact since the first message, e.g. latest number or a shipped item.} Happy to drop it if it's not relevant.
>
> Maxime

## T5. Last follow-up at 14 days, no reply

> Subject: Re: {original subject}
>
> Hi {first name}, last note from me on this. If the timing is wrong, no problem; I'll keep you posted only if you'd like to be on my short monthly update. Just reply "yes".
>
> Maxime

After T5 with no reply: set status to `cold` and do not contact again for 90 days.

## T6. Ask permission for the monthly update

After a call or a positive reply.

> Subject: Monthly ARP update?
>
> Hi {first name}, thanks again for {the call / your reply}. I send a short monthly update on ARP: three numbers, what shipped, what's next. No asks unless I need a specific intro. Want to be on it?
>
> Maxime

## T7. Thank you after a meeting (within 24 hours)

> Subject: Thanks, {first name}
>
> Hi {first name}, thanks for the time today. Noted your point on {their specific point from Maxime's notes}; I'll come back on it in the {month} update.
>
> Maxime

## T8. Monthly update

Use the template in `fundraising/03-monthly-update.md` exactly. Recipients: every pipeline row with `status = on_update_list`, in BCC. Numbers come from the Intuition query; if it cannot be run, leave the three numbers as `{to fill}` and say so in the recap.
