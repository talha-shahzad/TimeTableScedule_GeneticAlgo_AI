# TimeTableScedule_GeneticAlgo_AI
Project Description:
Timetable scheduling problem is a classical problem in the university environment where a
timetable is to be made individually for each semester ensuring minimum number of clashes
between sections, professors, and rooms. Thus, we have a timetabling problem where time slots
are assigned to each section in a particular room to be taught by a particular professor to teach
a particular course.
Please note that each week, there are 2 classes per theory course (each of 1 hour 20 mins
length), and lab courses will have a single long session of 3 hours.
The following constraints need to be followed:
Hard Constraints:
These are the constraints that need to be implemented in your project completely and without
any compromises.
• Classes can only be scheduled in free classrooms.
• A classroom should be big enough to accommodate the section. There should be two
categories of classrooms: classroom (60) and large hall (120).
• A professor should not be assigned two different lectures at the same time.
• The same section cannot be assigned to two different rooms at the same time.
• A room cannot be assigned for two different sections at the same time.
• No professor can teach more than 3 courses.
• No section can have more than 5 courses in a semester.
• Each course would have two lectures per week not on the same or adjacent days.
• Lab lectures should be conducted in two consecutive slots.

• 15 mins breaks allowed between consecutive classes to ensure that there is sufficient
time for transitions between classes.
Soft Constraints:
These are the constraints where some compromise can be expected. Hence, you are expected
to implement them as best as possible.
• All the theory classes should be taught in the morning session and all the lab sessions
should be done in the afternoon session.
• Teachers/students may be facilitated by minimizing the number of floors they have to
traverse. That is, as much as possible, scheduled classes should be on the same floor for
either party.
• A class should be held in the same classroom across the whole week.
• Teachers may prefer longer blocks of continuous teaching time to minimize
interruptions and maximize productivity except when the courses are different.
Other Details:
• The timetable should cover all the 5 days of the week with the morning session from
8:30 – 2:30 and the afternoon session from 2:30 – 5:30.
• The chromosomes should be binary encoded with the following information:
o Course, Theory/Lab, Section, Section-Strength, Professor, First-lecture-day,

First- lecture-timeslot, First-lecture-room, First-lecture-room-size, Second-
lecture-day, Second-lecture-timeslot, Second-lecture-room, Second-lecture-
room-size

• The fitness function should be an inverse or negative of the sum of all the
conflicts/clashes.

Execution Plan:
•	Initialization: The project starts by defining the necessary parameters such as courses, teachers, sections, classrooms, labs, days, time slots, and other constraints.
•	Creating Classes and Time Slots: Functions are defined to create classes (classrooms and labs) and generate time slots based on the provided parameters.
•	Timetable Generation: A function called TimeTableGenrator() is implemented to randomly assign courses, teachers, sections, and rooms to each time slot of each day. This generates a basic timetable with random allocations.
•	Chromosome Representation: Timetable entries are converted into chromosomes, which represent potential solutions. Each chromosome includes details such as course, type (theory/lab), section, teacher, day, time slot, room, room size, and a hash value for uniqueness.
•	Fitness Function: A fitness function is designed to evaluate the quality of each timetable (chromosome) based on certain criteria such as teacher workload, section overloading, room conflicts, and lecture distribution.
•	Genetic Operators: Parent selection, crossover, and mutation functions are implemented. Parent selection involves generating multiple timetables and selecting the best two. Two-point crossover is applied to exchange information between parents, and mutation introduces random changes to offspring.
•	Running the Genetic Algorithm: The genetic algorithm iterates over multiple generations. Every generation includes a new offspring, which are then generated through crossover and mutation, and the fittest individuals are selected to form the next generation. This process keeps on going for a certain number of generations.
•	Encoding Data: The function `encode_data` takes a list of chromosomes as input. It starts by initializing an empty list called `encoded` to store the encoded data. Then, it iterates through each chromosome in the input list. For each chromosome, it initializes an empty string called `hash_str`. Within each chromosome, it checks whether the element is a string or an integer. If it's a string, it iterates through each character, converts it to its binary representation using the `ord` function, pads it to 8 bits with leading zeros using `zfill`, and appends it to `hash_str`, separated by '|'. After each string, it appends ':' to separate different parts. If the element is an integer, it converts it to its binary representation, pads it to 32 bits, and appends it to `hash_str`, followed by ';'. Finally, after processing all elements in a chromosome, it appends '!' to mark the end of the chromosome and adds `hash_str` to the `encoded` list.
•	Decoding the data back to original: This function, named decode_data, takes in some encoded data as input. It first initializes an empty list called decoded. Then, it goes through each string in the input list encoded. For each string, it splits it into parts based on the '!' character. Then, for each part, it checks if it ends with a ':' character. If it does, it splits that part into characters using the ':' character as a delimiter. For each character, it further splits it into binary strings using '|' as a delimiter. It converts these binary strings into characters and appends them to a list called decoded_chromosome. If a part doesn't end with ':', it splits it into numbers using ';' as a delimiter and converts them from binary to integers, appending them to decoded_chromosome. Finally, it appends decoded_chromosome to the decoded list. Once all strings in encoded have been processed, the function returns the decoded list, which contains the decoded data, revealing the original information from the encoded input.


Future Enhancements:
•	Fine-tuning Fitness Function: Refining the fitness function to consider additional constraints or preferences, such as optimizing room capacities, minimizing gaps between classes, or accommodating preferences of teachers and students.
•	Dynamic Parameters: Making parameters such as class durations, break times, or the number of classes per day dynamic based on real-world requirements or user inputs.
•	Constraint Handling: Implementing more sophisticated methods to handle constraints, such as incorporating penalty functions or advanced constraint satisfaction techniques.

Results:
The implemented Genetic Algorithm successfully generates timetables that satisfy basic constraints and preferences. Even though this code functions and does everything that the requirements said to do, there can be further improvements in this code. We can refine and improve testing for better scalability and a more improved real-life application.

