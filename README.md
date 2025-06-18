# Validation rules for `Gift Card Form`
The gift card purchase form implements **client-side validation** using vanilla JavaScript to ensure data accuracy and improve user experience.

Check the `Gift Card Form` on this web site:<br>
<a href="https://www.rekasmassage.nl" target="_blank" rel="noopener noreferrer"><strong><i>Reka's Massage</i></strong></a>

Go to the article:<br>
<a href="https://www.linkedin.com/feed/update/urn:li:activity:7331971879450140673/" target="_blank" rel="noopener noreferrer"><strong><i>Digital Gift Card, UX e Sicurezza: una nuova esperienza utente!
</i></strong></a>

<!-- 
Problema:
GitHub rimuove o ignora l'attributo target="_blank" nei file .md, anche se uso un tag HTML come <a> nel Markdown. 
Questo accade perché GitHub utilizza un parser Markdown sicuro (come cmark-gfm) 
che filtra alcuni attributi ritenuti potenzialmente rischiosi.
-->

<br>

<h2>The features</h2>

📞 Field `#phone_number` – User phone number
- **Valid input**: digits only (`0–9`)
- **Real-time validation**: any non-numeric character is dynamically removed (`\D`).
- **Goal**: ensure clean and compliant phone numbers.


🌍 Field `#country_code` – International dialing code
- **Valid input**: only the `+` symbol (mandatory in the first position) followed by digits (`0–9`)
- **Real-time validation**:
  - Removes all invalid characters (`[^+\d]`)
  - If `+` is typed elsewhere, it is automatically moved to the beginning.
- **Goal**: compliance with international standard E.164.


💳 Field `#gcard_amount` – Gift card amount
- **Valid input**: numeric digits only
- **Limit**: maximum of 4 digits
- **Real-time validation**: input is filtered and truncated to 4 numeric characters (`slice(0, 4)`).
- **Goal**: prevent invalid entries and enforce business limits on the gift card amount.


⚙️ Technical Details
- Validations are triggered via the `input` event to provide immediate feedback to users.
- The `inputmode="numeric"` attribute is used to enhance mobile usability.
- JavaScript validation supports the UI, but **server-side validation remains essential** for data integrity and security.


💡 **Note**: All functionalities are implemented using pure JavaScript, with no external dependencies, ensuring maximum performance and cross-browser compatibility.