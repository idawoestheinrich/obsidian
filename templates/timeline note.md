```dataviewjs
let tasks = dv.pages('"research"')  // adjust path to your notes
  .where(t => t.start && t.end);
var section = "name"
var task = "task"
var start = "date"
var best = ""
var worst = ""
let gant = `\ngantt \n
    dateFormat  YYYY-MM-DD \n
    axisFormat  %d.%m\n
    title Project Timeline (Best vs Worst Case)\n`;
for (let t of tasks){
	section = t.file.name
	task = t.task
	start = t.start
	best = t.best_duration
	worst = t.worst_duration
	gant += `section ${section}\n
	${task} (Best Case)     :active, ${section}, ${start}, ${best}d\n
    ${task}(Latest Finish) :crit, ${section}, ${start}, ${worst}d\n`
}

dv.paragraph("```mermaid" + gant
    + "```")

    ```
  