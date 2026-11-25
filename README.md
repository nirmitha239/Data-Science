# GroupDNA: your WhatsApp group chat, decoded

A text-mining notebook that reads a WhatsApp chat export and produces a "Spotify Wrapped for your friend group" report: who spams, who ghosts, who is the night owl, which words the group is obsessed with, and a personality archetype for every member.

<img width="788" height="757" alt="Screenshot 2026-11-25 153215" src="https://github.com/user-attachments/assets/4e159a34-fddd-4373-a8c1-e44a87343c12" />
: `![GroupDNA report](report.png)`

## Results on hostel_bois.txt
3,174 messages, 6 members, 60 days. Rahul = THE SPAMMER, Priya = THE GROUP MOM, Neha = THE DRAMA QUEEN, Aman = THE NIGHT OWL (79.8% of messages between 23:00 and 04:59), Karan = THE STORYTELLER, Vikas = THE GHOST (silent on 44 of 60 days, longest silent streak 11 days).

## What it does
1. **Parser**: reads the export line by line and handles system messages, `<Media omitted>`, deleted messages, multi-line messages and empty lines.
2. **Group overview**: totals, date range, messages per person with bars.
3. **Busiest day and hour**.
4. **Activity heatmap**: a 6 x 24 NumPy matrix (person x hour) drawn with block characters.
5. **Top words**: group-wide and per person, with stop words removed.
6. **Response speed and silent streaks** using `datetime`.
7. **Archetypes**: eight rules from the brief plus one invented archetype (The Hype Beast), assigned exclusively using a documented tie-breaking rule.
8. **Final report**: one formatted, screenshot-ready printout, tested on an empty file and a one-person chat.

## Constraints (what I allowed myself)
- **Allowed:** Python fundamentals, lists, tuples, sets, dicts, NumPy, `open()`, `datetime.strptime` and `timedelta`, string methods, `sorted()` with `key=`.
- **Forbidden:** pandas, matplotlib, seaborn, plotly, `collections.Counter`, `collections.defaultdict`, `re`, any chat-analyzer library, any ML library.

## How to run
1. Open `GroupDNA_Nirmitha_037.ipynb` in Google Colab.
2. Click **Runtime → Run all**. Step 0 writes `hostel_bois.txt` into the session. (You can also upload your own `hostel_bois.txt` next to the notebook.)

## Build log
Day 1 parser, Day 2 overview, Day 3 word frequency, Day 4 NumPy heatmap, Day 5 response times and streaks, Day 6 archetypes, Day 7 polish, edge-case tests and README.

## AI disclosure
Parts of this project were written with help from Claude. Every AI-assisted cell is marked with an `# AI-assisted:` comment at the top.
