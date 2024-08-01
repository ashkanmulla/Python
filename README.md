https://maillink.predictiveindex.com/ls/click?upn=u001.MxnoiZZVDI-2BYg7DNaG92RudOYw-2BXjtxESgjG1-2FLOSLWJ-2FgOSPylVeNcSGNHKniy3dgawT2AFzqlyNru-2BmYRlid6mAZworO42upCsghMXSWj-2BEXC44LWmfnvTscBYXQ1yS9A1_6msc9UexehvC4lRUqAXu5wRNSCECvVaisSBhQ8Z-2ByXpy7lC5lVby133ZWzHkcYVaxl-2FTu-2B-2ByHGtTIqb18ESbBeO9BfbD1RYB4emmvB1KMivIVQs37egoX6NnNoFmzOb0Lrg3BMnzxU7qZIzvQUVqd93cM8PGB7umN-2BrCYPd-2B6HlC-2FBrrUM2VsPavITVjVmCbaXyMfFAIpPVXOkzltOaQZaParbSQHevgEwE3pthXYBJTH7QtBhm6uQHaNcICVxGm4-2BgjY-2Fr4rP1mbJKVCg-2FDZoesXZ8giBK57bNwglrynsDZfOx1pxzEZRsRBe3PM3lPi7iK-2FkIGMy1y36UJYbQUP6hMLj1AGNYhFCfdGAyzpdc-3D

https://link.edgepilot.com/s/f19d8e36/Ri4ACZa6v0GUX8Vmysz1bw?u=https://assessment.predictiveindex.com/bo/u37/CAorUW2022

def calculateScore(text, prefixString, suffixString):
    def longest_suffix_prefix_match(text, prefixString, suffixString):
        # Find longest match for prefix score
        max_prefix_score = 0
        prefix_match = ""
        for i in range(len(prefixString)):
            if text.startswith(prefixString[i:]):
                score = len(prefixString) - i
                if score > max_prefix_score:
                    max_prefix_score = score
                    prefix_match = prefixString[i:]

        # Find longest match for suffix score
        max_suffix_score = 0
        suffix_match = ""
        for i in range(1, len(suffixString) + 1):
            if text.endswith(suffixString[:i]):
                score = i
                if score > max_suffix_score:
                    max_suffix_score = score
                    suffix_match = suffixString[:i]

        return prefix_match, suffix_match, max_prefix_score, max_suffix_score

    max_score = 0
    result = text

    for i in range(len(text)):
        for j in range(i + 1, len(text) + 1):
            substring = text[i:j]
            prefix_match, suffix_match, prefix_score, suffix_score = longest_suffix_prefix_match(substring, prefixString, suffixString)
            current_score = prefix_score + suffix_score
            if current_score > max_score or (current_score == max_score and substring < result):
                max_score = current_score
                result = substring

    return result

# Sample Input
text = "nothing"
prefixString = "bruno"
suffixString = "ingenious"

# Expected Output: "nothing"
print(calculateScore(text, prefixString, suffixString))

# Sample Input
text = "ab"
prefixString = "b"
suffixString = "a"

# Expected Output: "a"
print(calculateScore(text, prefixString, suffixString))
