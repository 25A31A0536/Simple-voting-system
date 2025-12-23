# Simple-voting-system
C program project
#include <stdio.h>
#define CANDIDATES 4
#define VOTERS 10

int main() {
    int votes[CANDIDATES] = {0};
    int choice, i;
    char names[CANDIDATES][20] = {"Candidate A", "Candidate B", 
                                  "Candidate C", "Candidate D"};
    
    printf("Simple Voting System
");
    printf("====================
");
    
    // Voting loop for each voter
    for (i = 1; i <= VOTERS; i++) {
        printf("
Voter %d:
", i);
        printf("Choose candidate (0-%d):
", CANDIDATES-1);
        for (int j = 0; j < CANDIDATES; j++) {
            printf("%d. %s
", j, names[j]);
        }
        scanf("%d", &choice);
        
        if (choice >= 0 && choice < CANDIDATES) {
            votes[choice]++;
            printf("Vote cast for %s!
", names[choice]);
        } else {
            printf("Invalid choice!
");
        }
    }
    
    // Display results
    printf("
=== RESULTS ===
");
    for (i = 0; i < CANDIDATES; i++) {
        printf("%s: %d votes
", names[i], votes[i]);
    }
    
    // Find winner using loop
    int max_votes = 0, winner = 0;
    for (i = 0; i < CANDIDATES; i++) {
        if (votes[i] > max_votes) {
            max_votes = votes[i];
            winner = i;
        }
    }
    printf("
Winner: %s (%d votes)
", names[winner], max_votes);
    
    return 0;
}
