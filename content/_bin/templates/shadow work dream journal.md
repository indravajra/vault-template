<%*
// Initial setup
let dreamTitle, dreamMood, dreamSleepQuality, dreamNarrative, dreamSymbolsThemes, dreamEmotions, dreamRecurringPatterns, dreamTriggers, dreamInterpretations, dreamActions, dreamReflection;

// Prompt for the dream title
dreamTitle = await tp.system.prompt("Dream Title");
await tp.file.rename(dreamTitle);

// YAML front matter
tR += `---
id: ${tp.file.creation_date("YYYYMMDDHHmmss")}
title: "${dreamTitle}"
date: ${tp.date.now("YYYY-MM-DD")}
tags: [journals/dream]
---

`;

// Dream Details section
tR += "## Dream Details\n";
tR += `- **Title:** ${dreamTitle}\n`;
tR += `- **Date:** ${tp.date.now("YYYY-MM-DD")}\n`;
tR += `- **Time:** ${tp.date.now("HH:mm")}\n`;

// Mood upon waking using suggester with emojis
let moodOptions = {
  "Content": "😊 Content - A state of satisfaction",
  "Reflective": "😔 Reflective - Deep in thought",
  "Frustrated": "😠 Frustrated - Experiencing irritation",
  "Neutral": "😐 Neutral - Neither here nor there; balanced",
  "Anxious": "😱 Anxious - Feeling worry or unease",
  "Tired": "😴 Tired - In need of rest",
  "Overwhelmed": "🤯 Overwhelmed - Burdened by too much",
  "Loved": "🥰 Loved - Feeling affection and warmth",
  "Sad": "😢 Sad - Experiencing sorrow",
  "Angry": "😡 Angry - Feeling or showing strong annoyance",
  "Pensive": "🤔 Pensive - Engaged in deep or serious thought",
  "Relieved": "😌 Relieved - No longer feeling distressed"
};
dreamMood = await tp.system.suggester(Object.values(moodOptions), Object.keys(moodOptions));
tR += `- **Mood:** ${dreamMood}\n`;

// Sleep Quality
let sleepQualityOptions = ["Excellent", "Good", "Fair", "Poor", "Very Poor"];
dreamSleepQuality = await tp.system.suggester(sleepQualityOptions, sleepQualityOptions);
tR += `- **Sleep Quality:** ${dreamSleepQuality}\n\n`;

// Dream Narrative
dreamNarrative = await tp.system.prompt("Describe the dream in as much detail as possible:");
tR += "## Narrative\n" + dreamNarrative + "\n\n";

// Symbols and Themes
dreamSymbolsThemes = await tp.system.prompt("List any symbols or themes from the dream:");
tR += "## Symbols and Themes\n" + dreamSymbolsThemes + "\n\n";

// Emotions
dreamEmotions = await tp.system.prompt("What emotions did you experience during the dream?");
tR += "## Emotions\n" + dreamEmotions + "\n\n";

// Recurring Patterns
dreamRecurringPatterns = await tp.system.prompt("Have you experienced this dream or similar ones before?");
tR += "## Recurring Patterns\n" + dreamRecurringPatterns + "\n\n";

// Possible Triggers
dreamTriggers = await tp.system.prompt("Reflect on the previous day's events. Any triggers for the dream?");
tR += "## Possible Triggers\n" + dreamTriggers + "\n\n";

// Interpretations
dreamInterpretations = await tp.system.prompt("What do you think this dream might be telling you?");
tR += "## Interpretations\n" + dreamInterpretations + "\n\n";

// Actions
dreamActions = await tp.system.prompt("Are there any actions you feel compelled to take as a result of this dream?");
tR += "## Actions\n" + dreamActions + "\n\n";

// Reflection
dreamReflection = await tp.system.prompt("Write down any additional thoughts or feelings about the dream");
tR += "## Reflection\n" + dreamReflection + "\n\n";

tR += "## References\nInclude any references to dream symbols or psychology resources that you consulted for this dream.\n";
%>
