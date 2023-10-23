# Hadoop MapReduce Word Frequency Analysis

## Project Description
This project demonstrates a classic example of leveraging Hadoop MapReduce to conduct word frequency analysis on text data. Through this project, you can count the occurrence of each word within a specified text file, such as a book. The implementation uses the MapReduce paradigm, which is designed to process data in a distributed environment efficiently. A local aggregation feature is incorporated to enhance performance, providing an insightful and efficient means of text analysis.

## Getting Started

### Prerequisites
- Ensure that you have Java installed on your machine.
- Hadoop installed and configured on your machine.

### Setting up Hadoop MapReduce
Make sure that your Hadoop cluster is up and running before proceeding.

## Code Structure

### `WC_Mapper.java`
This file contains the mapper class responsible for tokenizing each line of text and emitting a key-value pair for each word. The key is the word, and the value is an integer 1, indicating one occurrence of the word.

### `WC_Reducer.java`
This file contains the reducer class which aggregates the word occurrences emitted by the mapper, summing them up to get the total count for each word.

### `WC_Runner.java`
This file is the driver class that configures and runs the Hadoop job. It sets up the job with the necessary configurations, including setting the input and output paths, specifying the mapper and reducer classes, and launching the job.

## Usage

### Compilation
Compile your Java files into a JAR file using the following command:

```bash
hadoop com.sun.tools.javac.Main WC_Mapper.java WC_Reducer.java WC_Runner.java
jar cf wc.jar WC_Mapper*.class WC_Reducer*.class WC_Runner*.class
```

### Execution
Run your Hadoop job with the following command:

```bash
hadoop jar wc.jar WC_Runner /path/to/input /path/to/output
```

Replace `/path/to/input` and `/path/to/output` with the actual paths to your input and output directories, respectively.

### Output
After successful execution, the output containing word counts will be stored in the specified output directory. Each line in the output file will contain a word followed by its frequency in the text.

## Contributing
If you wish to contribute to this project, feel free to fork the repository and submit a pull request.
