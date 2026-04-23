let taskId = 0;

/* Add Task */
function addTask(columnId) {
  const input = document.getElementById(`${columnId}-input`);
  const text = input.value.trim();

  if (!text) return;

  const task = document.createElement("div");
  task.className = "task";
  task.draggable = true;
  task.id = `task-${taskId++}`;
  task.innerText = text;

  task.addEventListener("dragstart", dragStart);

  document.getElementById(columnId).appendChild(task);
  input.value = "";
}

/* Drag Start */
function dragStart(e) {
  e.dataTransfer.setData("text/plain", e.target.id);
}

/* Allow Drop */
function allowDrop(e) {
  e.preventDefault();
}

/* Drop Task */
function drop(e) {
  e.preventDefault();

  const id = e.dataTransfer.getData("text/plain");
  const task = document.getElementById(id);

  const column = e.target.closest(".column");
  if (column) {
    column.appendChild(task);
  }
}

/* Highlight Drop Area */
const columns = document.querySelectorAll(".column");

columns.forEach(column => {
  column.addEventListener("dragover", (e) => {
    e.preventDefault();
    column.classList.add("drag-over");
  });

  column.addEventListener("dragleave", () => {
    column.classList.remove("drag-over");
  });

  column.addEventListener("drop", (e) => {
    drop(e);
    column.classList.remove("drag-over");
  });
});
