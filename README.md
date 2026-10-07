# 🔢 Subarray Sum Equals K

A C++ solution to find the **number of continuous subarrays whose sum is equal to a given target `k`**.

This solution uses the **Prefix Sum + Hash Map** technique to achieve efficient `O(n)` time complexity.

---

## 🚀 Problem

Given an integer array `arr` and an integer `k`, find the total number of continuous subarrays whose sum is exactly equal to `k`.

### Example

```text
Input:
arr = [1, 2, 3]
k = 3

Output:
2                    ┌─────────────┐
                    │    START    │
                    └──────┬──────┘
                           ↓
              ┌──────────────────────┐
              │ Input Array & Target │
              │         k            │
              └──────────┬───────────┘
                         ↓
              ┌──────────────────────┐
              │ Calculate Prefix Sum │
              └──────────┬───────────┘
                         ↓
              ┌──────────────────────┐
              │ Initialize count = 0 │
              │ Create Hash Map       │
              └──────────┬───────────┘
                         ↓
              ┌──────────────────────┐
              │ Traverse Prefix Sum  │
              └──────────┬───────────┘
                         ↓
                ┌─────────────────┐
                │ prefixSum[j] == │
                │       k ?       │
                └───────┬─────────┘
                    Yes │   │ No
                        ↓   │
                  ┌─────────┐
                  │ count++ │
                  └────┬────┘
                       │
                       ↓
             ┌────────────────────┐
             │ val = prefixSum[j] │
             │       - k          │
             └─────────┬──────────┘
                       ↓
                ┌───────────────┐
                │ Is val in Map?│
                └───────┬───────┘
                    Yes │   │ No
                        ↓   │
                 ┌──────────────┐
                 │ count +=     │
                 │ m[val]       │
                 └──────┬───────┘
                        │
                        ↓
             ┌──────────────────────┐
             │ Update Hash Map with │
             │ current Prefix Sum   │
             └──────────┬───────────┘
                        ↓
                 ┌───────────────┐
                 │ More Elements? │
                 └───────┬───────┘
                     Yes │   │ No
                         │   ↓
                         │ ┌─────────────┐
                         │ │ Return count│
                         │ └──────┬──────┘
                         │        ↓
                         │ ┌─────────────┐
                         │ │     END     │
                         │ └─────────────┘
                         │
                         └──→ Next Element
