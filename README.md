def maxLen(arr):
    # m stores {prefix_sum: index}
    m = {}
    cur_sum = 0
    res = 0
    
    for i in range(len(arr)):
        cur_sum += arr[i]
        
        if cur_sum == 0:
            res = i + 1
        
        # If sum seen before, subarray between those indices has sum 0
        if cur_sum in m:
            res = max(res, i - m[cur_sum])
        else:
            m[cur_sum] = i
            
    return res

# Testing with your example
arr = [15, -2, 2, -8, 1, 7, 10, 23]
print(maxLen(arr)) # Output: 5
# -Kanagavalli-Program-5
