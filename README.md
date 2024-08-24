# Scalable-voting-systems

A scientific methodology for creating scalable voting systems that enable collective preferences to be ranked, aggregated and measured in compliance with all of Arrow's rationality criteria

# Strategic Optimization of Social Welfare (SOW)

**Version 1.0** | Released 3 days ago by **Oli-Roc**

Welcome to the Strategic Optimization of Social Welfare (SOW) project! This repository is dedicated to the development and implementation of voting algorithms and applications that adhere to the five criteria of Arrow's Impossibility Theorem. We invite developers from around the world to collaborate on creating robust voting procedures that enhance democratic processes and collective decision-making.

## Project Overview

Managing to classify, aggregate, and measure collective preferences is the central subject of study in Social Choice Theory (SCT). For centuries, it was believed that designing a perfect voting system that meets all rationality criteria was impossible, as demonstrated by Arrow's Impossibility Theorem. However, our project provides groundbreaking methodologies to construct decision-making procedures that comply with all five of Arrow's criteria: universality, independence, non-dictatorship, unanimity, and sovereignty.

### Key Contributions

- **Scalable Decision-Making Procedures**: Our methodologies are designed to be scalable and economically deployable across various scales, from small communities to national electoral systems.
- **New Voting Algorithms**: We introduce a set of decision-making procedures that align with Arrow's criteria, promoting both resilience and adaptability.
- **Strategic Goal Alignment**: Our framework includes strategies to build decision-making procedures that align with the strategic goals and values of organizations.
- **Candidate Suitability Analysis**: Provides insights into which types of candidates are best suited for each voting procedure.
- **Wide Range of Applications**: Identifies various fields of application across disciplines, such as economics, political science, and organizational management.

## Why This Project Matters

- **Guidance for Developers**: This repository offers comprehensive documentation and resources to help developers understand and implement voting algorithms that enhance democratic representation.
- **Improving Collective Intelligence**: By developing better voting systems, we aim to strengthen the principles of democracy and improve the functioning of collective intelligence in decision-making processes.
- **Open Source and Free Access**: This knowledge is shared openly to ensure it remains a resource for public benefit and is protected against misappropriation or distortion.

## Installation

To clone the repository and install dependencies, run the following commands:

```bash
git clone https://github.com/Oli-Roc/SOW.git
cd SOW
pip install -r requirements.txt
```

## Voting procedures of the document

Our repository contains a scientific paper that proposes a battery of different voting procedures that are all formalised to meet all the Arrow's rationality criteria. 
This makes it possible to develop different voting algorithms based on the same methodology. 

1. Plurality Rule (Leximax Ordering):

This voting method focuses on identifying a single most preferred alternative. It is characterized by maximizing the satisfaction of the most satisfied individuals, thereby aligning with elitist strategies.
In this system, voters can approve a single alternative (1-approval voting), and the alternative with the most votes wins. This method favors "exclusive" candidates who are highly preferred by a subset of voters but may not have broad approval.
The plurality rule is strong on support as it prioritizes alternatives that receive the highest number of first-choice votes, disregarding the preferences of the less satisfied voters.

2. Approval Voting:

Voters can approve multiple alternatives without ranking them. Each approved alternative gets one point, and the alternative with the highest total points is selected.
This method is weakly approval-oriented, focusing on minimizing rejection rather than maximizing strong support. It is often used to find a broadly acceptable option rather than a highly preferred one.
The system is ideal for identifying "inclusive" candidates who may not be the top choice but are widely acceptable to a large portion of voters.

3. Borda Count:

A scoring system where voters rank alternatives, and points are assigned based on the position in each voter’s ranking. The alternative with the highest total score wins.
The Borda count is a hybrid approach that balances support and approval. It considers all rankings, thus favoring alternatives that are generally well-regarded across the board, rather than just the most or least preferred.
This method is weakly consensus-oriented and is suitable for situations where both broad acceptability and moderate support are desired.

4. Nash Value:

This method uses a geometric weighting system to evaluate alternatives based on a product of utilities (or satisfactions) across all voters.
It emphasizes a balance between individual satisfaction and collective agreement, making it suitable for scenarios where strategic decisions need to be both resilient and inclusive.
The Nash value is highly approval-oriented and prioritizes alternatives that have a reasonable level of support and are acceptable to a majority.

5. Median Voting Rules (e.g., Bucklin and Majority Judgment):

These rules determine the winning alternative based on the median voter’s preference, often resolving ties using additional criteria.
Such methods aim to reflect the central tendency of voter preferences and are highly suitable for finding a compromise that balances support and approval.
Majority judgment, in particular, evaluates alternatives by considering the median evaluation across all voters, making it a robust choice for achieving consensus in diverse groups.

6. Support and Approval Vectors:

The document introduces new concepts like support and approval vectors to represent voter preferences more accurately. Support measures how many voters rank an alternative among their top choices, while approval quantifies the proportion of voters who do not reject the alternative.
These vectors allow for more nuanced voting procedures that can adapt to both elitist and egalitarian strategies, depending on how they are aggregated and interpreted.

7. Hybrid Voting Rules:

The document also proposes hybrid rules that combine elements of different traditional methods to achieve a balance between various strategic objectives, such as maximizing utility, ensuring fairness, and promoting inclusivity.

Examples include combining support and approval measures with different weightings to tailor the voting process to specific strategic goals of the organization or group. Possible weightings for support and approval vectors include an efficient voting procedure based on the golden ratio.

These procedures are designed to provide more flexible, scalable, and resilient decision-making processes, addressing the limitations of traditional voting systems by adhering to Arrow's criteria while incorporating innovative strategies to improve democratic representation and collective intelligence.

## Contributing

We welcome contributions from the global developer community. If you would like to contribute:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with a detailed description of your changes.

Please ensure your code adheres to our coding standards and includes appropriate tests.

## License

This project is licensed under a Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

Special thanks to the contributors and researchers whose work has inspired and guided this project. We also acknowledge the use of third-party libraries and tools.

## Additional Resources

- [Condorcet Paradox](https://en.wikipedia.org/wiki/Condorcet_paradox)
- [Arrow's Impossibility Theorem](https://en.wikipedia.org/wiki/Arrow%27s_impossibility_theorem)
- [Related Research and Publications](https://www.iddri.org/sites/default/files/import/publications/an_0804.collectivepreferences.pdf)

For more detailed information, please refer to our full article published on GitHub.

## Contact

For any questions or further information, feel free to contact us:

- **Olivier Rocca**: roccaolivier@yahoo.fr

Join us in revolutionizing the future of democratic decision-making!

