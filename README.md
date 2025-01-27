# XCodeTipsAndTricks

This repository contains handy code snippets and examples featured on our YouTube channel, <a href="https://www.youtube.com/@ioscribbler/videos" target="_blank"><b>ioscribbler</b></a>.

## Introduction

If you visit our channel, you'll find a series of videos focusing on how to effectively utilize Xcode shortcuts in real-life coding scenarios. Over the years, I’ve relied on various tips and shortcuts in Xcode that have made tasks like legacy code refactoring, reformatting, and editing much easier. 🛠️

This repository complements that series by providing code snippets for nearly every part of it. You can copy these snippets into your local Xcode environment and try out the tips for yourself!


## <a name="snippets">📦 Snippets(Code to Copy)</a>

<details>
<summary><code>Part1: Split Function Arguments.swift</code></summary>
<br>
 
```swift
class TaskManager {
    private var tasks: [TaskItem] = []

    func addTaskItem(title: String, description: String, dueDate: Date, priority: Int) {
        let task = TaskItem(title: title, description: description, dueDate: dueDate, priority: priority)
        tasks.append(task)
        print("Task added successfully!")
    }

    func updateTaskItem(id: UUID, newTitle: String?, newDescription: String?,
                        newDueDate: Date?, newPriority: Int?) {
        guard let index = tasks.firstIndex(where: { $0.id == id }) else {
            print("Task not found!")
            return
        }
        if let title = newTitle {
            tasks[index].title = title
        }
        if let description = newDescription {
            tasks[index].description = description
        }
        if let dueDate = newDueDate {
            tasks[index].dueDate = dueDate
        }
        if let priority = newPriority {
            tasks[index].priority = priority
        }
        print("Task updated successfully!")
    }

    func fetchTaskItems(filterByPriority: Int? = nil, sortByDueDate: Bool = false) -> [TaskItem] {
        var filteredTasks = tasks
        if let priority = filterByPriority {
            filteredTasks = filteredTasks.filter { $0.priority == priority }
        }
        if sortByDueDate {
            filteredTasks.sort { $0.dueDate < $1.dueDate }
        }
        return filteredTasks
    }
}
```
</details>

<details>
<summary><code>Part2: Multiple Cursors.swift</code></summary>
<br>
 ```swift
 struct AccountDetailsResponse: Decodable {
    let name: String
    let age: Int
    let email: String
    let phoneNumber: String
    let accessId: Int
    let accountRating: Int
}
 ```
</details>

