# Minimize-Changes-to-Embed-Substring

In a land of mysterious codes, you are given two enchanted strings, X and Y. Your mission is to transform string X so that Y appears as a continuous sequence within it. However, you can only achieve this by changing a few characters in X. Your goal is to figure out the minimum number of character changes required to ensure Y becomes a perfect substring of X, unlocking the hidden magic within the strings.

def minimize_changes_to_embed_substring(X, Y):

    len_X = len(X)
    len_Y = len(Y)
    min_changes = float('inf')  

    for i in range(len_X - len_Y + 1):
        changes = 0
        for j in range(len_Y):
            if X[i + j] != Y[j]:
                changes += 1
        min_changes = min(min_changes, changes)

    return min_changes

X = input().strip()
Y = input().strip()

print(minimize_changes_to_embed_substring(X, Y))
