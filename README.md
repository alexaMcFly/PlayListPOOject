# Project: Music File Manager
This project manages data from song files and implements efficient functions for data insertion and filtered search, along with appropriate sorting methods for presenting the data. In this stage, the sorting methods are implemented within the project.

## Progress Description 1
Sorting methods appropriate for the data handled in the project are implemented, specifically for song titles, authors, and durations.

## Progress Description 2
A **Queue** data structure is implemented to play a list of songs that have been previously sorted alphabetically.

### Changes in the First Progress
1. **Change 1**: I corrected the sorting of the songs, as there was a mismatch between the data. Initially, only the song duration was being rearranged, and the titles, authors, and genres were not being sorted together.

## Progress Description 3
Code cleanup by creating functions for each part of the program to enable a more in-depth algorithmic analysis.

### Changes in the Second Progress
I created functions for each section of the program, leaving only function calls in `main()` depending on which feature needs to be executed.

## Instructions to Compile the Project's Progress
Press the "Run" button to compile and execute the project.

## Instructions to Execute the Project's Progress
Press the "Run" button to compile and execute the project.

## Input Description for the Project's Progress
The input required is a text file (.txt) where each line contains the song title, author, and duration in minutes, with the data separated by a hyphen ("-"). Example: *Sweet Child´o Mine-Guns´n Roses-356*.

## Output Description for the Project's Progress
The output displays the songs in ascending order by duration in the console, and the user is given the option to sort the songs alphabetically by genre.

## Competency Development

### SICT0301: Evaluates components
#### Makes a correct and complete complexity analysis for the sorting algorithms used in the program.
The **Merge Sort** algorithm is used to sort a long list (the total number of songs based on their duration) with a time complexity of **O(n log(n))** in all cases. This makes it a highly reliable and stable algorithm in terms of performance, ensuring no concerns about execution time. While **Merge Sort** uses additional memory, there are no limitations on this resource, making it ideal for this case. 

Compared to **Quick Sort**, which is typically slightly faster, **Merge Sort** has a more consistent worst-case performance.

On the other hand, **Shell Sort** has a time complexity of **Θ(n(log(n))^2)** on average and in the worst case, while the best-case complexity is **Ω(n log(n))**. While slightly more challenging to implement than quadratic algorithms like **Bubble Sort** and **Selection Sort**, its worst-case execution time is significantly lower.

#### Makes a correct and complete complexity analysis of all the data structures and their uses in the program.
The complexity of creating the queue when the user selects the genre they want to play is **O(n)**. For example, if the playlist the user wants to play has 10 songs, it will take 10 operations to add elements to the queue.

Similarly, for playback, the number of operations required to remove and display the songs in the queue depends on the number of songs. 

Accessing information in the playlist is **O(1)**, as I only need to access the first element of the queue.

#### Makes a correct and complete complexity analysis for all other components of the program and determines the overall complexity.
To meet this competency, I determined the time complexity for each function in the program, focusing on the worst-case scenarios. According to Big-O notation, the overall complexity of the program is determined by the most complex function, which is **shellSort**. Therefore, the final complexity in the worst case is **Θ(n(log(n))^2)**.

For the best case scenario, the complexity is **O(n log(n))**.

### SICT0302: Makes decisions
#### Selects and correctly uses an appropriate sorting algorithm for the problem.
I chose the **Merge Sort** algorithm to sort all the songs from the file (approximately 1000 elements), as it is one of the most efficient algorithms for sorting large datasets. Additionally, **Merge Sort** is a stable algorithm, meaning that previously ordered data remains in order during the sorting process, making it even more efficient.

I also decided to use **Shell Sort** for sorting elements within specific playlists, considering that a playlist will typically have between 20-100 elements. **Shell Sort** offers efficient performance for small lists and is simpler to implement. While it is not a stable algorithm like **Merge Sort**, I believe **Shell Sort** is a good option for lists of this size.

#### Selects and correctly uses an appropriate data structure for the problem.
I chose to use a **Queue** to manage the playback of a song list. The process involves sorting songs by genre or playlist in a vector and then adding them to the queue in the sorted order. The songs are played back, with the first song to be played being the first one added to the queue. The queue employs **enqueue** to add songs at the end and **dequeue** to remove songs from the beginning.

### SICT0303: Implements scientific actions
#### Correctly implements mechanisms for querying data from the structures.
To query data in my program, I use the **front** method, which returns the first element of the queue. I used this to display the songs in the playback queue in the console after each song was played. Once the song finished, I removed the first element from the queue and retrieved the new first element.

#### Implements mechanisms for reading files to load data into the structures correctly.
The file-reading mechanism in my project uses the **iostream** library in C++. For practicality, the file is read line by line, and based on the specific file format, the songs and their details are processed to create objects for playlists and songs. These song objects are then added to the playback queue as per the user's request.

#### Implements mechanisms for writing files to correctly store data from the structures.
I implemented file writing using the **ofstream** function to generate a history of songs played by the user during each session. Currently, the file is overwritten every time the program runs. The songs the user plays are written to this file, but not the playlists created during execution. This mechanism acts as a playback history.
