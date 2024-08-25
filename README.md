# GSoC 2024 Project Blog

Blog link: https://nj221102.github.io/Nitish-gSoc-24/

# Summary of my GSoC 2024
## Basic Info
- **Name**: Nitish Jha
- **Email**: nitishj221102@gmail.com
- **Github Username**: Nj221102
- **Mentors**: Toby Dylan Hocking, Anirban chetia
- **Project Title**: Enhancing Data.Table
- **Project Link**: [data.table](https://github.com/Rdatatable/data.table)

### Work Summary

During this period, significant progress was made on multiple fronts, including resolving critical issues and enhancing the functionality of the `data.table` package. Below is a summary of the work done:

Apologies for the misunderstanding. Here's the corrected table with the pattern you described:

| Issues | Pull Requests |
| :------ |:--- |
| [Export masks for all NSE-only constructs #5604](https://github.com/Rdatatable/data.table/issues/5604) | [#6125](https://github.com/Rdatatable/data.table/pull/6125) |
| [patterns function missing #5277](https://github.com/Rdatatable/data.table/issues/5277) | [#6125](https://github.com/Rdatatable/data.table/pull/6125) |
| [.NATURAL is missing from ?".N" #4930](https://github.com/Rdatatable/data.table/issues/4930) | [#6155](https://github.com/Rdatatable/data.table/pull/6155) |
| [Query a non-existing element #5292](https://github.com/Rdatatable/data.table/issues/5292) | [#6184](https://github.com/Rdatatable/data.table/pull/6184) |
| [Add a section to datatable-importing vignette#6037](https://github.com/Rdatatable/data.table/issues/6037) | [#6161](https://github.com/Rdatatable/data.table/pull/6161) |
| [dcast: add argument to error on "Aggregate function missing #5386](https://github.com/Rdatatable/data.table/issues/5386) | [#6164](https://github.com/Rdatatable/data.table/pull/6164) |
| [Suggestion: Warn when making integer column key #5074](https://github.com/Rdatatable/data.table/issues/5074) | [#6189](https://github.com/Rdatatable/data.table/pull/6189) |
| [add examples of set function in documentation #5031](https://github.com/Rdatatable/data.table/issues/5031) | [#6190](https://github.com/Rdatatable/data.table/pull/6190) |
| [Unexpected behavior in .BY #5389](https://github.com/Rdatatable/data.table/issues/5389) | [#6193](https://github.com/Rdatatable/data.table/pull/6193) |
| [Improve the documentation for fromLast in unique #5130](https://github.com/Rdatatable/data.table/issues/5130) | [#6195](https://github.com/Rdatatable/data.table/pull/6195) |
| [TRUE/FALSE and abbreviated variants T/F have different behavior #4846](https://github.com/Rdatatable/data.table/issues/4846) | [#6196](https://github.com/Rdatatable/data.table/pull/6196) |
| [revdep issues caused when . and J are exported #6197](https://github.com/Rdatatable/data.table/issues/6197) | [#6198](https://github.com/Rdatatable/data.table/pull/6198), [#6200](https://github.com/Rdatatable/data.table/pull/6200),  [#6207](https://github.com/Rdatatable/data.table/pull/6207) |
| [shift wrong behavior for list columns #5188](https://github.com/Rdatatable/data.table/issues/5188) | [#6201](https://github.com/Rdatatable/data.table/pull/6201) |
| [Be more outspoken on distinction between week and isoweek functions #3065](https://github.com/Rdatatable/data.table/issues/3065) | [#6237](https://github.com/Rdatatable/data.table/pull/6237) |
| [setnames() errors silently ignored in full assignment (no 'old') #6236](https://github.com/Rdatatable/data.table/issues/6236) | [#6273](https://github.com/Rdatatable/data.table/pull/6273) |
| [Issue with datat.table:: namespace appending (NSE) #5357](https://github.com/Rdatatable/data.table/issues/5357) | [#6302](https://github.com/Rdatatable/data.table/pull/6302) |
| [rbindlist gives wrong results when applied objects with different units.#4541](https://github.com/Rdatatable/data.table/issues/4541) | [#6309](https://github.com/Rdatatable/data.table/pull/6309) |
| [text labels for months / weekdays #1286](https://github.com/Rdatatable/data.table/issues/1286) | [#6310](https://github.com/Rdatatable/data.table/pull/6310) |
| [error with set() or := NULL to a list column item #5526](https://github.com/Rdatatable/data.table/issues/5526) | [#6336](https://github.com/Rdatatable/data.table/pull/6336) |
| [Document well how to flexibly pass functions in env= #6323](https://github.com/Rdatatable/data.table/issues/6323) | [#6360](https://github.com/Rdatatable/data.table/pull/6360) |
| [openmp documentation misses freadR.c file #5265](https://github.com/Rdatatable/data.table/issues/5265) | [#6162](https://github.com/Rdatatable/data.table/pull/6162) |
| [C forder could take verbose argument #4533](https://github.com/Rdatatable/data.table/issues/4533) | [#6179](https://github.com/Rdatatable/data.table/pull/6179) |
| [fwrite() should (possibly invisibly) return the file path #5706](https://github.com/Rdatatable/data.table/issues/5706) | [#6181](https://github.com/Rdatatable/data.table/pull/6181) |
| [Add new argument skip_absent= for colnamesInt() #6067](https://github.com/Rdatatable/data.table/issues/6067) | [#6068](https://github.com/Rdatatable/data.table/pull/6068) |
| [Use selective imports #5970](https://github.com/Rdatatable/data.table/issues/5970) | [#5988](https://github.com/Rdatatable/data.table/pull/5988) |


## **Overview**

Being part of Google Summer of Code this year has been an incredible experience. I’m immensely grateful to my mentor for giving me the opportunity to work on this project and for the guidance provided along the way. This journey has significantly boosted my coding skills and confidence, allowing me to explore new areas of software development.

As a student, balancing academic responsibilities with my commitment to this project has been challenging, yet rewarding. The experience taught me valuable time management skills, as I dedicated evenings and weekends to contributing to the project. The support and flexibility offered by my mentor were essential in helping me navigate these challenges.

Overall, my first Google Summer of Code has been about more than just writing code; it’s been a journey of learning, adaptation, and growth. I’m eager to apply what I’ve learned to continue improving the project and to contribute more to the open-source community.

## **Acknowledgments**

I would like to express my deepest gratitude to my mentors, Toby Dylan Hocking and Anirban Chetia. Throughout this summer, they have been invaluable guides, patiently helping me navigate the complexities of coding and consistently encouraging me to think critically and write well-structured code. Their quick responses and insightful feedback have been instrumental in my learning process, often shedding light on issues I hadn’t even considered.

The data.table community has also been a tremendous support, generously providing guidance and sharing their wealth of knowledge. Their feedback has helped me refine my approach and better understand the intricacies of the project. I truly appreciate everyone's patience and encouragement, which have been a constant source of motivation throughout this journey.

Lastly, I want to thank my fellow GSoC contributors for their camaraderie and support. It’s been a great experience working alongside such a talented and supportive group.