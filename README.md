# micar-whitepaper-template

A MiCAR crypto-asset white paper template with continuous linting. Fill in `whitepaper.json`; each push to `main` and each pull request runs [micar-whitepaper-linter](https://github.com/sebastianfoerste/micar-whitepaper-linter), which lists each open finding with its citation under **Actions**. In report mode (`strict: 'false'`) open findings do not fail the check; a file the linter cannot load (invalid JSON, unknown `"type"`) does. Set `strict: 'true'` in the workflow to fail on any open (Review or Missing) BLOCKER.

Or lint [in the browser](https://sebastianfoerste.github.io/micar-whitepaper-linter/playground/); nothing you paste leaves the page.

## How to use it

1. **Use this template** (private is fine).
2. Replace every `REPLACE:` placeholder; each names the disclosure its section must carry. The linter reads an untouched placeholder as text, not as a gap, so search for leftovers yourself.
3. Set `"type"` to `art`, `emt` or `other`. The placeholders describe an asset-referenced token (Art. 19 and Annex II MiCAR); for `emt` or `other`, the linter warns about keys it does not read and names the sections it lacks. Add those and rewrite the existing placeholders for your type.
4. Push, work the findings down, then hand the draft to counsel.

## What the linter checks

Deterministic checks: keywords, minimum length and structure per required section and annex item, LEI check digits, file format; the linter does not judge whether a disclosure is accurate or adequate. Two BLOCKERs never pass for this draft: the iXBRL format check (the notification format is XHTML with Inline XBRL, not JSON) and, for an asset-referenced token, the deposit floor of the reserve of assets (Art. 35(4), 36(4)(d), 45(3) and 45(7)(b) MiCAR), left to a lawyer; a strict build therefore always fails. The workflow follows the linter's `@v1` tag, which moves with each v1 release; see its changelog for changes.

## Scope and honesty

- Not legal advice. A green check never means the white paper is lawful, complete or ready to notify or submit for approval. That judgment stays with your lawyer.
- Content requirements only, not the authorisation or notification procedure.
- Synthetic guidance; nothing describes a real issuer or token.

## License

MIT, like the [linter](https://github.com/sebastianfoerste/micar-whitepaper-linter).
