---
title: "Simulating Quantum Circuits with Non-Clifford Noise"
collection: publications
category: manuscripts
permalink: /publication/2024-08-15-QuantumNoise
excerpt: ' We introduce the basics of quantum computing and simulation of quantum systems on classical computers. We then discuss noise in quantum systems and how instances of noise are classically modelled, along with the difficulties of simulating quantum noise on classical computers. We introduce an extension of the T-Gadget to classically simulate thousands of instances of dampening noise within reasonable memory constraints.'
date: 2024-08-15
#venue: 'Journal 1'
slidesurl: 'http://jad_soucar.github.io/files/QuantumNoise_Slides.pdf'
paperurl: 'http://jad_soucar.github.io/files/QuantumNoise.pdf'
#bibtexurl: 'http://academicpages.github.io/files/bibtex1.bib'
#citation: 'Jad Soucar, Ninaad Surana. (2024). &quot;Autonomous Trading Using Deep Q Learning &quote;'
---

We introduce the basics of quantum computing and simulation of quantum systems on classical computers. We then discuss noise in quantum systems and how it is classically modelled, along with the difficulties of simulating quantum noise on classical computers. Our primary question is how to efficiently simulate quantum noise by leveraging existing techniques based upon the Gottesman-Knill theorem, which provides efficient simulation of circuits containing only Clifford gates. We follow this by describing our progress thus far in exploring three primary approaches. First, exploring methods to decompose a noise operator into a sum of cliffords via mixed integer linear programming and using these decompositions to classically simulate noisy quantum circuits within the stabilizer formalism first proposed by Aaronson and Gottesman (2004). We find that the a Clifford decomposition is not guaranteed to have low rank decompositions and that at best the runtime of simulating noise using Clifford decompositions would be $$O(2^k)$$, where $$k$$ is the number of Kraus operators applied. Second, we explore the process of dilating our space to convert our noise operators into unitaries in a larger space. Specifically we propose two unitary dilation based algorithms for simulating noise; Sz.-Nagy and Stinespring's dilation algorithms. The two algorithms yield respective run-times of 

$$O(\frac{1}{\delta \Delta^2} sn^3 \eta^{-2} 1.17^{t})$$ 

$$O\left(n^2 \prod_{i=1}^k \left|\xi_i\right| + n^3 \sum_{i=1}^k \left|\xi_i\right|^3\right)$$ 

Third we propose a theoretical framework for generalizing the T-Gadget approach developed by  Bravyi and Gosset (2016). Through numerical simulations we show that the generalized framework can be used to produce noise simulation algorithms with efficient runtime and space complexity. 
