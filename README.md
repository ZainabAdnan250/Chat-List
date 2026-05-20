# Chat List 

A lightweight, single-file chat list UI built with vanilla HTML, CSS, and JavaScript.

---

## Features

| Feature | Details |
|---|---|
| **Add Chat** | FAB (`+`) opens a floating form. Fill name, message, time, and gender, then click *Add Chat*. |
| **Delete Chat** | Click the 🗑️ button on any chat item to remove it instantly. |
| **Edit Name** | Click the ✏️ button to open a modal and rename a contact. |
| **Search by Name** | Type in the search bar at the top — list filters in real time, case-insensitive. |
| **XSS Protection** | All user input is HTML-escaped before rendering (`escape()` helper), preventing script injection. |
| **Inline Validation** | Required fields, max-length checks, and gender selection are all validated with visible inline error messages — no `alert()` dialogs. |
| **Gender Avatars** | Male / Female avatars auto-assigned based on selected gender. |

---



## Security Notes

### XSS Prevention
User-supplied values (`name`, `message`, `time`) are passed through `escape()` before being written to the DOM:

```js
function escape(str) {
  return String(str)
    .replace(/&/g, "&amp;")
    .replace(/</g, "&lt;")
    .replace(/>/g, "&gt;")
    .replace(/"/g, "&quot;")
    .replace(/'/g, "&#039;");
}
```

This prevents payloads like `<script>alert(1)</script>` from executing.

---

## Validation Rules

| Field   | Rule |
|---------|------|
| Name    | Required · Max 40 characters |
| Message | Required · Max 120 characters |
| Time    | Required |
| Gender  | Must select Male or Female |
| Edit Name | Required · Max 40 characters |

Errors appear as red text beneath each field and clear as soon as the user starts correcting them.

---

## License
MIT- free to use modify and distribute.

## 📌 Live Preview 

Explore the project here 👉 https://zainabadnan250.github.io/Chat-List/
