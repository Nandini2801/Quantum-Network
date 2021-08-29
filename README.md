# Quantum-Network
This repo contains the QKD protocols used for secret communication over a quantum channel

BB84 Protocol:
The understanding and implementation of the protocol was taken from  the research paper "QUANTUM CRYPTOGRAPHY: PUBLIC KEY DISTRIBUTION AND COIN TOSSING"
link: https://drive.google.com/file/d/1sn7UG0Pfr0lx3CFo4bjGTAevJbdlLx3o/view?usp=sharing
One user ('Alice') chooses a random bit string and a random sequence of polarization bases (rectilinear or diagonal). She then
sends the other user (Bob) a train of photons, each representing one bit of the string in the basis chosen for that bit position, a horizontal or 45-degree
photon standing for a binary zero and a vertical or 135-degree photon standing for a binary 1. As Bob receives the photons, he decides, randomly for each
photon (independently of Alice), whether to measure the photon's rectilinear polarization or its diagonal polarization and interprets the result of
the measurement as a binary zero or one.

All information gets lost when one attempts to measure the rectilinear polarization of a diagonal photon or vice versa. Thus Bob obtains meaningful data from only half the photons he detects those for which he guessed the correct polarization basis.


Subsequent steps of the protocol occur over an ordinary public communications channel, assumed to be susceptible to eavesdropping but not to
the injection or alteration of messages. Bob and Alice first determine, by public exchange of messages, which photons were successfully received and received with the correct basis.

Alice and Bob should agree on the bits encoded by these photons; even this data has never been discussed over the public channel. Each of these photons, in other words, presumably carries one bit of random information (e.g., whether a rectilinear photon was vertical or horizontal) known to Alice and
Bob but to no one else.
Due to the random mix of rectilinear and diagonal photons in the quantum transmission, any eavesdropping carries the risk of altering the information in such a way as to produce disagreement between Bob and Alice on some of the bits on which they think they should agree. 

Alice and Bob can therefore test for eavesdropping by publicly comparing some of the bits on which they think they should agree, though, of course, this sacrifices the secrecy of these bits. The bit positions used in this comparison should be a random subset (say one-third) of the correctly received bits so that eavesdropping on more than a few photons is unlikely to escape detection. If it agrees, Alice and Bob can conclude that the quantum transmission is free of significant eavesdropping; and those of the remaining bits that were sent and received with the same basis also agree and can safely be used as a one-time pad for subsequent secure communications over the public channel. When this one-time pad is used up, the protocol is repeated to send a new body of random information over the quantum channel. 

![image](https://user-images.githubusercontent.com/63334774/131251165-ec04411d-8482-4696-965f-66de6dae59f0.png)
