# Word-Chain-Pattern-Check

Leo has a sequence of N words and wants to ensure they follow a special pattern: each word, starting from the second one, must begin with the last letter of the previous word and must not repeat any word used earlier. Given the list of words, can you determine if they follow Leo’s pattern? Print “Yes” if they do, otherwise print “No.”

def word_chain_check(N, words):

    seen = set()
    for i in range(N):
        word = words[i]
        if word in seen:  # Check for repetition
            return "No"
        seen.add(word)
        if i > 0:  # Check last letter matching for second and subsequent words
            if words[i - 1][-1] != word[0]:
                return "No"
    return "Yes"

# Input
N = int(input())
words = [input().strip() for _ in range(N)]

# Output the result
print(word_chain_check(N, words))
