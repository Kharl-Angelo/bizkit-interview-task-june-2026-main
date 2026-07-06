## 📌 Important Note

It is better to read this by right clicking the file `NOTES.md` and then click **"Open Preview"** to review the formatted version. This helps you see the final structure, readability, and spacing before submission.

---

## Direction: Explain one fix

Pick any one of the bugs above and, in a few sentences, say what was actually wrong and how your fix addresses it.

### Answer:

For Task 2, the issue was the **PHP 0 booking bug**.

Both the frontend and backend calculate the total price by subtracting the start date from the end date to get the number of days, then multiplying it by the price.

However, when the start date and end date are the same, the difference becomes **0 days**. As a result, the total price is also calculated as 0 because any number multiplied by zero is zero.

The fix is to properly handle same-day bookings so that they are counted as at least **1 day**, instead of 0.

---

## Direction: Show the failure

For the double-booking bug (Task 1), give one concrete example — just the dates — of a booking the original code wrongly allowed, but that your fix now correctly blocks. One line is fine.

### Answer:

For example, if there is an existing booking for a Canon DSLR Camera from:

* **2026-07-03 to 2026-07-07**

Then a new booking is submitted with:

* **2026-07-02 to 2026-07-07** (or **2026-07-10**)

The system incorrectly allows this booking even though it overlaps with the existing reservation. Instead of preventing it, the booking proceeds.

In short, with existing data:

```json id="p8qk3a"
{
    "equipment_id": 1,
    "equipment_name": "Canon DSLR Camera",
    "from_date": "2026-07-03",
    "to_date": "2026-07-07"
}
```

And a new request:

```json id="m1zv2k"
{
    "equipment_id": 1,
    "equipment_name": "Canon DSLR Camera",
    "from_date": "2026-07-02",
    "to_date": "2026-07-07"
}
```

(or)

```json id="x9ld0c"
{
    "equipment_id": 1,
    "equipment_name": "Canon DSLR Camera",
    "from_date": "2026-07-02",
    "to_date": "2026-07-10"
}
```

The system still allows the booking instead of blocking the overlap.

---

## Direction: AI use

Tell us roughly what you used AI tools for, if anything — and, importantly, how you checked that its output was correct.

### Answer:

I used AI tools as a guide to support my work and ensure everything is implemented correctly.

For this task, I mainly used AI for paraphrasing my comments to make them clearer and more aligned with the solution I implemented. I also used it to help review or refine parts of the solution when I felt I might have missed something.

Before using AI suggestions, I first defined my own logic and approach for solving the problem. My main understanding and implementation always came first. I then used AI to validate my approach or explore better alternatives when needed.

After receiving suggestions, I reviewed and made sure I fully understood them before applying any changes to my code.
