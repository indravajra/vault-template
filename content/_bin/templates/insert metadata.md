<%*
// Ask the user to input the title if it starts with "Untitled"
let title = tp.file.title;
if (title.startsWith("Untitled")) {
  title = await tp.system.prompt("Title");
  await tp.file.rename(title);
}

// Convert title to uppercase and strip unwanted characters
let title_uppercase = title.replace(/\b\w/g, c => c.toUpperCase());
let result = title_uppercase.replace(/[^a-zA-Z0-9 ]/g, '');

// YAML front matter start
tR += "---\n";
tR += `id: ${tp.file.creation_date("YYYYMMDDHHmmss")}\n`;
tR += `title: "${result}"\n`;
tR += `created: ${moment(tp.file.creation_date("YYYY-MM-DDTHH:mm:ss.SSSZ")).toISOString()}\n`;
tR += "tags:\n";

// Suggester for general categories
let generalTag = await tp.system.suggester(["journals", "projects", "topics", "references", "archives", "private", "canvas"], ["journals", "projects", "topics", "references", "archives", "private", "canvas"], true);
if (generalTag) {
  tR += `  - ${generalTag}\n`;
}

// Combined options for state display and corresponding tags
let noteStateOptions = [
  { display: "Seed Idea - Initial thoughts or questions", tag: "state/seed" },
  { display: "In Process - Ideas being actively developed", tag: "state/process" },
  { display: "Permanent Note - Well-developed, interconnected ideas", tag: "state/permanent" },
  { display: "Reference Material - Supporting information and data", tag: "state/reference" },
  { display: "Incubating - Ideas on hold but considered for future development", tag: "state/incubating" },
  { display: "Question - Notes that are primarily questions", tag: "state/question" },
  { display: "Project - Notes associated with specific projects or actionable goals", tag: "state/project" },
  { display: "Archived - No longer actively relevant but retained for future reference", tag: "state/archived" },
  { display: "None - Undecided state", tag: "none" }
];

// Suggester for note states
let selectedOption = await tp.system.suggester(noteStateOptions.map(option => option.display), noteStateOptions.map(option => option.display), false, "Select the current state for this note:");
let selectedTag = noteStateOptions.find(option => option.display === selectedOption)?.tag;

if (selectedTag && selectedTag !== "none") {
  tR += `  - ${selectedTag}\n`;
}

// YAML front matter end
tR += "---";
%>
