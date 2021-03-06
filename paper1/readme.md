# Using Large-Scale Anomaly Detection on Code to Improve kotlin compiler
 ## AUTHORS NAME

Timofey Bryksin, Victor Petukhov, Ilya Alexin, Stanislav Prikhodko, Alexey
Shpilman, Vladimir Kovalenko, and Nikita Povarov. 2020.
 
## CONFERENCE NAME:
>Mining Software Repositories (MSR'20),

Using LargeScale Anomaly Detection on Code to Improve Kotlin Compiler. In 17th
International Conference on Mining Software Repositories (MSR ’20), October
5–6, 2020, Seoul, Republic of Korea. ACM, New York, NY, USA, 11 pages.

## INTRODUCTION:
In software engineering,anomalytechniqueshave been successfully applied to a variety of practical tasks in many areas. 
These techniques help to detect cyberattacks,identify pathologies in medical images and detect traces of fraudulent activities in financial data.       
In Software engineering, anomaly detection is widely applied to findind bugs, security issues, workflow errors and other anomalous patterns in code or others software artifacts.
we propose a new area of application for anomaly detection, finding issues in programming language compilers.
we define a code that are not typical wittin the community or an ecosystem of a giving programming language or machine code that is uncharacteristic within the range of output produced by the compiler.
such code should be useful to both users and developers of the language.  
Established industry of standard languages such as Java and C++ are not the more feasible targets for detecting  anomiles at the scale of a language ecosystem. 
while large amounts of open source codein these languages are publicly available, mainstream compilers are very well-tested and stable, which makes it hard to identify unknown compiler issues through anomaly detection.
we choose kotline and its ecosystem as a target for this study. 
Since the language is relatively young, its compiler might still contain bugs and performance issues.
The paper is all about threefold:
.A method for finding code anomalies
.A set of tools implementing the proposed method and as well as more than four million unique kotline functions collected from GitHub and the bytecode.
. The evalution of the proposed method on the collected dataset

## RESEARCH METHODOLOGY:
The GrouMiner tool was developed to detect anomalous patterns in object interaction in java programs.
The tool performs a static code analysis.
Contextual anomalies occur when a single data object is anomalous in a specific context but not otherwise.
Collective anomalies occur when linked objects are observed against other objects as an anomaly.
Syntax trees encoding the latent vector of a nuetral network autoencoder and other distributed code representation.
We perform a search for code anomalies in kotlin programs that are written specifically for the JVM, since it comprises the majority of code written in kotlin.
Our goal is to detect two types of anomiles: syntax tree anomalies and compiler-induced anomalies.
A compiler-induced anomaly is a code fragment that is not an anomaly in the syntax tree form but is an anomaly in the bytecode or vice versa.
We choose to call them compiler-induced because their anomalous nature is revealed only after their bytecode is obtained and analyzed.
To collect a large dataset, we cloned GitHubrepositories that were created before March 2018,stated Kotlin as their main language, and were not forks of some other projects.
We use software metrics and N-grams extraction to embed the syntax tree representation of the code
Software metrics are divided into 4 groups:
• general code metrics: the number of lines of code, the number
of nodes and the height of the syntax tree, etc.
• structural metrics: nesting depth, cyclomatic complexity,
number of branches in “when” expression, etc.
• external metrics of Kotlin functions: the formal arguments
number, type parameters, annotations, the presence of a
suspend modifier, etc.
• the number of particular language elements: expressions,
operators, keywords, function calls, string patterns, etc.
To assess the viability of our approach to identification of anomalies,we conduct an evaluation of significance and practical value of anomalies extracted from the dataset.

## RESULT:

In this summary i detect two kinds of experiments to different types of code anomalies (syntax tree anomalies and compilerinduced anomalies), using different approaches both at the code
vectorization and at the anomaly detection stages.As a result, 91
syntax tree anomalies and 54 compiler-induced anomalies were
presented for assessment of importance to the Kotlin compiler developers. According to the results of the assessment, 38 syntax tree
anomalies and 31 compiler-induced anomalies were considereduseful (they got rank values 4 and 5). Some of these anomalies were
added into the compiler testing infrastructure as performance and
correctness tests for the compiler front-end and back-end; several
anomalies were postponed for further discussion on possible language design issues. Based on these results and further discussions
with the Kotlin compiler developers, we believe that the detected anomalies are useful and valuable for the language development,and our proposed approach proved itself successful in detection ofvarious code anomalies. 
