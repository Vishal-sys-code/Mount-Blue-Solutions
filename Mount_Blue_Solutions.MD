# **MOUNT BLUE KA SOLUTIONS**

## **1. Sales by Match**

```py
def sockMerchant(n, ar):
    # Write your code here
    colors = {}
    for sock in ar:
      if sock in colors:
        colors[sock] += 1
      else:
        colors[sock] = 1
    return sum(color//2 for color in colors.values())
```

<hr>

## **2. Simple Array Sum**

```py
def simpleArraySum(ar):
    # Write your code here
    return sum(ar)
```

<hr>

## **3. Breaking Records**

```py
def breakingRecords(scores):
    # Write your code here
    max_break = 0
    min_break = 0
    max_score = scores[0]
    min_score = scores[0]
    for score in scores[1:]:
        if score > max_score:
            max_break += 1
            max_score = score
        elif score < min_score:
            min_break += 1
            min_score = score
    return [max_break, min_break]
```

<hr>

## **4. Number Line Jumps**

```py
def kangaroo(x1, v1, x2, v2):
    # Write your code here
    if v1 > v2 and (x2 - x1) % (v1 - v2) == 0:
        return "YES"
    else:
        return "NO"
```

<hr>

## **5. Staircase**

```py
def staircase(n):
    # Write your code here
    for i in range(1, n+1):
        print(" "*(n-i) + "#"*i)
```

<hr>

## **6. Compare the Triplets**

```py
def compareTriplets(a, b):
    # Write your code here
    alice = 0
    bob = 0
    for i in range(3):
        if a[i] > b[i]:
            alice += 1
        elif a[i] < b[i]:
            bob += 1
    return [alice, bob]
```


<hr>

## **7. Quicksort 1 - Partition**

```py
def quickSort(arr):
    # Write your code here
    n = len(arr)
    pivot = arr[0]
    left = [x for x in arr[1:] if x <= pivot]
    right = [x for x in arr[1:] if x > pivot]
    return left + [pivot] + right
```

<hr>

## **8. Between Two Sets**

```py
def gcd(a, b):
    if b == 0:
        return a
    return gcd(b, a % b)

def lcm(a, b):
    return a * b // gcd(a, b)

def gcd_array(a):
    res = a[0]
    for i in range(1, len(a)):
        res = gcd(res, a[i])
    return res

def lcm_array(a):
    res = a[0]
    for i in range(1, len(a)):
        res = lcm(res, a[i])
    return res



def getTotalX(a, b):
    # Write your code here
    lcm_a = lcm_array(a)
    gcd_b = gcd_array(b)
    count = 0
    i = lcm_a
    j = 2
    while i <= gcd_b:
        if gcd_b % i == 0:
            count += 1
        i = lcm_a * j
        j += 1
    return count
```

<hr>

## **9. Super Reduced String**

```py
def superReducedString(s):
    # Write your code here
    stack = []
    for c in s:
        if stack and stack[-1] == c:
            stack.pop()
        else:
            stack.append(c)
    return ''.join(stack) if stack else "Empty String"
```

<hr>

## **10. Bill Division**

```py

def bonAppetit(bill, k, b):
    # Write your code here
    bill.pop(k)
    if sum(bill) // 2 == b:
        print("Bon Appetit")
    else:
        print(b - sum(bill) // 2)
```

## **11. A Very Big Sum**

```py
def aVeryBigSum(ar):
    # Write your code here
    return sum(ar)
```

<hr>

## **12. Plus Minus**

```py
def plusMinus(arr):
    # Write your code here
    positive = 0
    negative = 0
    zero = 0
    for i in arr:
        if i > 0:
            positive += 1
        elif i < 0:
            negative += 1
        else:
            zero += 1
    print("{:.6f}".format(positive/len(arr)))
    print("{:.6f}".format(negative/len(arr)))
    print("{:.6f}".format(zero/len(arr)))
```

<hr>

## **13. Subarray Division**

```py
def birthday(s, d, m):
    # Write your code here
    count = 0
    for i in range(len(s)):
        if sum(s[i:i+m]) == d:
            count += 1
    return count
```

<hr>

## **14. Migratory Birds**

```py
def migratoryBirds(arr):
    # Write your code here
    bird_counts = [0,0,0,0,0,0]
    for bird in arr:
        bird_counts[bird] += 1
    max_sighting = max(bird_counts)
    for i in range(len(bird_counts)):
        if bird_counts[i] == max_sighting:
            return i
```

<hr>

## **15. Diagonal Difference**

```py

def diagonalDifference(arr):
    # Write your code here
    left = 0
    right = 0
    for i in range(len(arr)):
        left += arr[i][i]
        right += arr[i][len(arr)-1-i]
    return abs(left - right)
```

<hr>

## **16. Birthday Cake Candles**

```py

def birthdayCakeCandles(acandles):
    # Write your code here
    max_height = max(candles)
    count = 0
    for i in candles:
        if i == max_height:
            count += 1
    return count
```

<hr>

## **17. Grading Students**

```py
def gradingStudents(grades):
    # Write your code here
    for i in range(len(grades)):
        if grades[i] >= 38:
            if grades[i] % 5 >= 3:
                grades[i] += 5 - grades[i] % 5
    return grades
```

<hr>

## **18. Drawing Book**

```py
def pageCount(n, p):
    # Write your code here
    if n % 2 == 0:
        n += 1
    return min(p//2, n//2 - p//2)
```

<hr>

## **19. Divisible Sum Pairs**

```py
def divisibleSumPairs(n, k, ar):
    # Write your code here
    count = 0
    for i in range(n):
        for j in range(i+1, n):
            if (ar[i] + ar[j]) % k == 0:
                count += 1
    return count
```

<hr>

## **20. Mini-Max Sum**

```py
def miniMaxSum(arr):
    # Write your code here
    print(sum(arr) - max(arr), sum(arr) - min(arr))
```

<hr>

## **21. Counting Valleys**

```py
def countingValleys(n, s):
    # Write your code here
    level = 0
    valleys = 0
    for i in s:
        if i == 'U':
            level += 1
        else:
            level -= 1
        if level == 0 and i == 'U':
            valleys += 1
    return valleys
```

## **22. Libray Fine**

```py
def libraryFine(d1, m1, y1, d2, m2, y2):
    # Write your code here
    if y1 > y2:
        return 10000
    elif y1 == y2:
        if m1 > m2:
            return 500 * (m1 - m2)
        elif m1 == m2:
            if d1 > d2:
                return 15 * (d1 - d2)
    return 0
```

<hr>

## **23. Time Conversion**

```py
def timeConversion(s):
    # Write your code here
    if s[-2:] == 'PM' and s[:2] != '12':
        s = str(int(s[:2]) + 12) + s[2:]
    if s[-2:] == 'AM' and s[:2] == '12':
        s = '00' + s[2:]
    return s[:-2]
```

<hr>

## **24. Caesar Cipher**

```py
def caesarCipher(s, k):
    # Write your code here
    result = ''
    for c in s:
        if c.isalpha():
            if c.isupper():
                result += chr((ord(c) - ord('A') + k) % 26 + ord('A'))
            else:
                result += chr((ord(c) - ord('a') + k) % 26 + ord('a'))
        else:
            result += c
    return result
```

<hr>

## **25. Tower Breakers**

```py
def towerBreakers(n, m):
    # Write your code here
    if m == 1 or n % 2 == 0:
        return 2
    else:
        return 1
```

<hr>

## **26. Day of the Programmer**

```py
def dayOfProgrammer(year):
    # Write your code here
    if year == 1918:
        return '26.09.1918'
    elif year < 1918:
        if year % 4 == 0:
            return '12.09.' + str(year)
        else:
            return '13.09.' + str(year)
    else:
        if year % 400 == 0 or (year % 4 == 0 and year % 100 != 0):
            return '12.09.' + str(year)
        else:
            return '13.09.' + str(year)
```

<hr>

## **27. The Hurdle Race**

```py
def hurdleRace(k, height):
    # Write your code here
    return max(0, max(height) - k)
```

<hr>

## **28. Strong Password**

```py
def minimumNumber(n, password):
    # Return the minimum number of characters to make the password strong
    count = 0
    if not any(c.isdigit() for c in password):
        count += 1
    if not any(c.islower() for c in password):
        count += 1
    if not any(c.isupper() for c in password):
        count += 1
    if not any(c in '!@#$%^&*()-+' for c in password):
        count += 1
    return max(count, 6 - n)
```

<hr>

## **29. Minimum Absolute Difference in an Array**

```py
def minimumAbsoluteDifference(arr):
    # Write your code here
    arr.sort()
    min_diff = abs(arr[0] - arr[1])
    for i in range(1, len(arr) - 1):
        min_diff = min(min_diff, abs(arr[i] - arr[i+1]))
    return min_diff
```

<hr>

## **30. Mars Exploration**

```py
def marsExploration(s):
    # Write your code here
    count = 0
    for i in range(0, len(s), 3):
        if s[i] != 'S':
            count += 1
        if s[i+1] != 'O':
            count += 1
        if s[i+2] != 'S':
            count += 1
    return count
```

<hr>

## **31. Electronics Shop**

```py
def getMoneySpent(keyboards, drives, b):
    # Write your code here
    max_price = -1
    for i in keyboards:
        for j in drives:
            if i + j <= b:
                max_price = max(max_price, i + j)
    return max_price
```

<hr>

## **32. CamelCase**

```py
def camelcase(s):
    # Write your code here
    count = 1
    for c in s:
        if c.isupper():
            count += 1
    return count
```

<hr>

## **33. Viral Advertising**

```py
def viralAdvertising(n):
    # Write your code here
    shared = 5
    liked = 0
    cumulative = 0
    for i in range(n):
        liked = shared // 2
        cumulative += liked
        shared = liked * 3
    return cumulative
```

<hr>

## **34. Jumping on the Clouds: Revisited**

```py
def jumpingOnClouds(c, k):
    # Write your code here
    energy = 100
    i = 0
    while True:
        i = (i + k) % len(c)
        energy -= 1
        if c[i] == 1:
            energy -= 2
        if i == 0:
            break
    return energy
```

<hr>

## **35. Game of Stones**

```py
def gameOfStones(n):
    # Write your code here
    if n % 7 in [0, 1]:
        return 'Second'
    else:
        return 'First'
```

<hr>

## **36. Marc's Cakewalk**

```py
def marcsCakewalk(calorie):
    # Write your code here
    calorie.sort(reverse=True)
    miles = 0
    for i in range(len(calorie)):
        miles += calorie[i] * 2 ** i
    return miles
```

<hr>

## **37. Cats and a Mouse**

```py
def catAndMouse(x, y, z):
    # Write your code here
    if abs(x - z) < abs(y - z):
        return 'Cat A'
    elif abs(x - z) > abs(y - z):
        return 'Cat B'
    else:
        return 'Mouse C'
```

<hr>

## **38. Save the Prisoner!**

```py
def saveThePrisoner(n, m, s):
    # Write your code here
    return (s + m - 2) % n + 1
```

<hr>

## **39. Beautiful Days at the Movies**

```py
def beautifulDays(i, j, k):
    # Write your code here
    count = 0
    for n in range(i, j+1):
        if abs(n - int(str(n)[::-1])) % k == 0:
            count += 1
    return count
```

<hr>

## **40. Sequence Equation**

```py
def permutationEquation(p):
    # Write your code here
    result = []
    for i in range(1, len(p) + 1):
        result.append(p.index(p.index(i) + 1) + 1)
    return result
```

<hr>

## **41. Grid Challenge**

```py
def gridChallenge(grid):
    # Write your code here
    for i in range(len(grid)):
        grid[i] = sorted(grid[i])
    for i in range(len(grid[0])):
        for j in range(len(grid) - 1):
            if grid[j][i] > grid[j+1][i]:
                return 'NO'
    return 'YES'
```

<hr>

## **42. Angry Professor**

```py
def angryProfessor(k, a):
    # Write your code here
    count = 0
    for i in a:
        if i <= 0:
            count += 1
    if count >= k:
        return 'NO'
    else:
        return 'YES'
```

<hr>

## **43. Sherlock and Squares**

```py
import math

def squares(a, b):
    count = 0
    for i in range(math.isqrt(a-1) + 1, math.isqrt(b) + 1):
        if i**2 >= a and i**2 <= b:
            count += 1
    return count

```
<hr>

## **44.Circular Array Rotation**

```py
def circularArrayRotation(a, k, queries):
    n = len(a)
    k = k % n   # reduce k to the range [0, n)

    # Rotate the array
    rotated = [0] * n
    for i in range(n):
        rotated[(i + k) % n] = a[i]

    # Get the values at the given indices
    result = []
    for q in queries:
        result.append(rotated[q])

    return result

```

<hr>

## **45. Big Sorting**

```py
def bigSorting(unsorted):
    # Write your code here
    return sorted(unsorted, key=int)
```

<hr>

## **46. Equalize the Array**

```py
def equalizeArray(arr):
    # Write your code here
    return len(arr) - max(arr.count(i) for i in arr)
```

<hr>

## **47. Minimum Distances**

```py
def minimumDistances(a):
    # Write your code here
    min_dist = len(a)
    for i in range(len(a)):
        for j in range(i+1, len(a)):
            if a[i] == a[j]:
                min_dist = min(min_dist, j - i)
    if min_dist == len(a):
        return -1
    else:
        return min_dist
```

<hr>

## **48. Separate the Numbers**

```py

def separateNumbers(s):
    n = len(s)
    for i in range(1, n//2+1):
        f = int(s[:i])
        num = f
        j = i
        while j < n:
            if str(num+1) == s[j:j+len(str(num+1))]:
                num += 1
                j += len(str(num))
            else:
                break
        if j == n:
            print("YES " + str(f))
            return
    print("NO")

```

<hr>

## **49. The Love-Letter Mystery**

```py

def theLoveLetterMystery(s):
    # Write your code here
    count = 0
    for i in range(len(s)//2):
        count += abs(ord(s[i]) - ord(s[-i-1]))
    return count
```

<hr>

## **50. Halloween Sale**

```py

def howManyGames(p, d, m, s):
    # Return the number of games you can buy
    count = 0
    while s >= p:
        s -= p
        count += 1
        p = max(p - d, m)
    return count
```

<hr>

## **51. Maximum Perimeter Triangle**

```py

def maximumPerimeterTriangle(sticks):
    # Write your code here
    sticks.sort(reverse=True)
    for i in range(len(sticks) - 2):
        if sticks[i] < sticks[i+1] + sticks[i+2]:
            return [sticks[i+2], sticks[i+1], sticks[i]]
    return [-1]
```

<hr>

## **52. Alternating Characters**

```py
def alternatingCharacters(s):
    # Write your code here
    count = 0
    for i in range(len(s) - 1):
        if s[i] == s[i+1]:
            count += 1
    return count
```

<hr>

## **53. Pangrams**

```py
def pangrams(s):
    # Write your code here
    s = s.lower()
    for i in range(97, 123):
        if chr(i) not in s:
            return 'not pangram'
    return 'pangram'
```

<hr>

## **54. Beautiful Binary String**


```py
def beautifulBinaryString(b):
    # Write your code here
    return b.count('010')
```

<hr>

## **55. Utopian Tree**

```py

def utopianTree(n):
    # Write your code here
    height = 1
    for i in range(n):
        if i % 2 == 0:
            height *= 2
        else:
            height += 1
    return height
```

<hr>

## **56. Beautiful Triplets**

```py

def beautifulTriplets(d, arr):
    # Write your code here
    count = 0
    for i in range(len(arr)):
        if arr[i] + d in arr and arr[i] + 2*d in arr:
            count += 1
    return count
```

<hr>

## **57. Picking Numbers**

```py

def pickingNumbers(a):
    # Write your code here
    a.sort()
    max_count = 0
    for i in range(len(a)):
        count = 1
        for j in range(i+1, len(a)):
            if abs(a[i] - a[j]) <= 1:
                count += 1
        max_count = max(max_count, count)
    return max_count
```

<hr>

## **58. Repeated String**

```py

def repeatedString(s, n):
    # Write your code here
    count = 0
    for i in s:
        if i == 'a':
            count += 1
    count *= n // len(s)
    for i in s[:n % len(s)]:
        if i == 'a':
            count += 1
    return count
```

<hr>

## **59. HackerRank in a String!**

```py

def hackerrankInString(s):
    # The string we are looking for
    target = 'hackerrank'
    
    # The index of the next character we are looking for
    next_char = 0

    # Loop through the string

    for c in s:
        if c == target[next_char]:
            next_char += 1
            if next_char == len(target):
                return 'YES'
    return 'NO'
```

<hr>

## **60. Designer PDF Viewer**

```py

def designerPdfViewer(h, word):
    # Write your code here
    return len(word) * max(h[ord(i) - 97] for i in word)
```

<hr>

## **61. Service Lane**

```py
def serviceLane(n, cases):
    # Write your code here
    result = []
    for i, j in cases:
        result.append(min(width[i:j+1]))
    return result
```

<hr>

## **62. Lonely Integer**

```py

def lonelyinteger(a):
    # Write your code here
    for i in a:
        if a.count(i) == 1:
            return i
```

<hr>

## **63. Luck Balance**

```py

def luckBalance(k, contests):
    # Write your code here
    contests.sort(reverse=True)
    luck = 0
    for i in contests:
        if i[1] == 0:
            luck += i[0]
        elif k > 0:
            luck += i[0]
            k -= 1
        else:
            luck -= i[0]
    return luck
```

<hr>

## **64. Append and Delete**

```py

def appendAndDelete(s, t, k):
    # Write your code here
    if s == t:
        return 'Yes'
    for i in range(min(len(s), len(t))):
        if s[i] != t[i]:
            break
    if len(s) + len(t) - 2*i > k:
        return 'No'
    elif (len(s) + len(t) - 2*i) % 2 == k % 2:
        return 'Yes'
    elif len(s) + len(t) < k:
        return 'Yes'
    else:
        return 'No'
```

<hr>

## **65. Misère Nim**

```C++

// C++
string misereNim(vector<int> s) {

  int ans=0;int c=0;
  for(auto &it : s){
    ans^=it;
    if(it==1)
      c++;
  }
  
   return (ans==(c==s.size()))?"Second":"First";   
}
```

<hr>

## **66. Jumping on the Clouds**

```py

def jumpingOnClouds(c):
    # Write your code here
    count = 0
    i = 0
    while i < len(c) - 1:
        if i + 2 < len(c) and c[i+2] == 0:
            i += 2
        else:
            i += 1
        count += 1
    return count
```

<hr>

## **67. Gemstones**

```py

def gemstones(arr):
    # Write your code here
    count = 0
    for i in range(97, 123):
        for j in arr:
            if chr(i) not in j:
                break
        else:
            count += 1
    return count
```

<hr>

## **68. Two Strings**

```py

def twoStrings(s1, s2):
    # Write your code here
    for i in s1:
        if i in s2:
            return 'YES'
    return 'NO'
```

<hr>

## **69. Chocolate Feast**

```py

def chocolateFeast(n, c, m):
    # Write your code here
    count = n // c
    wrappers = count
    while wrappers >= m:
        count += wrappers // m
        wrappers = wrappers // m + wrappers % m
    return count
```

<hr>

## **70. ACM ICPC Team**

```py

def acmTeam(topic):
    # Write your code here
    max_topics = 0
    max_teams = 0
    for i in range(len(topic)):
        for j in range(i+1, len(topic)):
            topics = bin(int(topic[i], 2) | int(topic[j], 2)).count('1')
            if topics > max_topics:
                max_topics = topics
                max_teams = 1
            elif topics == max_topics:
                max_teams += 1
    return max_topics, max_teams
```

<hr>

## **71. Taum and B'day**

```py

def taumBday(b, w, bc, wc, z):
    # Write your code here
    return min(b*bc + w*wc, b*bc + w*(bc+z), b*(wc+z) + w*wc)
```

<hr>

## **72. Funny String**

```py

def funnyString(s):
    # Write your code here
    for i in range(1, len(s)):
        if abs(ord(s[i]) - ord(s[i-1])) != abs(ord(s[-i]) - ord(s[-i-1])):
            return 'Not Funny'
    return 'Funny'
```

<hr>

## **73. Sum vs XOR**

```py

def sumXor(n):
    if n == 0:
        return 1
    bin_n = bin(n)[2:]
    count = 1

    for i in bin_n:
        if i == '1':
            count = count * 1 
        else:
            count = count * 2 
    return count
```

<hr>

## **74. String Construction**

```py

def stringConstruction(s):
    # Write your code here
    return len(set(s))
```

<hr>

## **75. Find Digits**

```py

def findDigits(n):
    # Write your code here
    count = 0
    for i in str(n):
        if int(i) != 0 and n % int(i) == 0:
            count += 1
    return count
```

<hr>

## **76. Palindrome Index**

```py

def palindromeIndex(s):
    # Write your code here
    for i in range(len(s) // 2):
        if s[i] != s[-i-1]:
            if s[i+1] == s[-i-1] and s[i+2] == s[-i-2]:
                return i
            else:
                return len(s) - i - 1
    return -1
```

<hr>

## **77. Lisa's Workbook**

```py

def workbook(n, k, arr):
    # Write your code here
    count = 0
    page = 1
    for i in arr:
        for j in range(1, i+1):
            if j == page:
                count += 1
            if j % k == 0 and j != i:
                page += 1
        page += 1
    return count
```

<hr>

## **78. Smart Number**

```py
import math

def is_smart_number(num):
    val = int(math.sqrt(num))
    if val*val == num:
        return True
    return False

for _ in range(int(input())):
    num = int(input())
    ans = is_smart_number(num)
    if ans:
        print("YES")
    else:
        print("NO")
```

<hr>

## **79. XOR Strings**

```py

def strings_xor(s, t):
    res = ""
    for i in range(len(s)):
        if s[i] == t[i]:
            res += '0';
        else:
            res += '1';

    return res

s = input()
t = input()
print(strings_xor(s, t))
```

<hr>

## **80. Fair Rations**

```py

def fairRations(B):
    a=sum(B,0)
    if a%2!=0:
        return 'NO'
    else:
        c=0
        for i in range(len(B)-1):
            if B[i]%2!=0:
                B[i]=B[i]+1
                B[i+1]=B[i+1]+1
                c=c+2
        print(c)
        return str(c)
```

<hr>

## **81. Anagram**

```py

def anagram(s):
    if len(s) % 2 != 0:
        return -1
    else:
        s1 = s[:len(s)//2]
        s2 = s[len(s)//2:]
        count = 0
        for i in s1:
            if i in s2:
                s2 = s2.replace(i, '', 1)
            else:
                count += 1
        return count
```

<hr>

## **82. Cut the sticks**

```py

def cutTheSticks(arr):
    # Write your code here
    res = []
    while arr:
        res.append(len(arr))
        min_val = min(arr)
        arr = [i - min_val for i in arr if i - min_val > 0]
    return res
```

<hr>

## **83. Modified Kaprekar Numbers**

```py

def kaprekarNumbers(p, q):
    # Write your code here
    res = []
    for i in range(p, q+1):
        if i == 1:
            res.append(i)
        else:
            square = str(i**2)
            if len(square) == 1:
                continue
            else:
                if int(square[:len(square)//2]) + int(square[len(square)//2:]) == i:
                    res.append(i)
    if res:
        print(*res)
    else:
        print('INVALID RANGE')
```

<hr>

## **84. Sherlock and The Beast**

```cpp

//cpp
void decentNumber(int n) {
    int y = 0;
    for (; n - 5 * y >= 0; y++)
    {   
        if ((n - 5 * y) % 3 == 0)
            break;
    }
    int a = n - 5 * y;
    int b = 5 * y;
    if (a >= 0)
    {
        for (int i = 0; i < a; i++)
            cout << 5;
        for (int i = 0; i < b; i++)
            cout << 3;
        cout << "\n";
    }
    else{
        cout << -1 << "\n";
    }
}

```

<hr>

## **85. Game of Thrones - I**

```java

//java
public static String gameOfThrones(String s) {
    // Write your code here
        String khaleesi = "YES";
        List<Character> d = new ArrayList<>();
        for(int j = 0;j<s.length();j++){
            if(!d.contains(s.charAt(j)))d.add(s.charAt(j));
        }
        if(s.length() % 2 == 0){
            for(char c : d){
                if(s.codePoints().filter(ch -> ch == c).count() % 2 != 0)return "NO";
            }
        }
        else{
            int n = 0;
            for(char c : d){
                if(n>1)return "NO";
                if(s.codePoints().filter(ch -> ch == c).count() % 2 != 0)n++;
            }
        }
        return khaleesi;

}
```

<hr>

## **86. Maximizing XOR**

```py

def maximizingXor(l, r):
    # Write your code here
    return max([i^j for i in range(l, r+1) for j in range(i, r+1)])
```

<hr>

## **87. Happy Ladybugs**

```py
from collections import Counter
from itertools import groupby

def happyLadybugs(b):
    c = Counter(b)
    if "_" in c:
        c.pop("_")
        if all(v > 1 for v in c.values()):
            return "YES"
        else:
            return "NO"
    else:
        if all(len(list(g)) > 1 for k, g in groupby(b)):
            return "YES"
        else:
            return "NO"
```

<hr>

## **88. Counting Sort 1**

```py

def countingSort(arr):
    # Write your code here
    res = [0]*100
    for i in arr:
        res[i] += 1
    return res
```

<hr>

## **89. Priyanka and Toys**

```py

def toys(w):
    # Write your code here
    w.sort()
    res = 1
    curr = w[0]
    for i in w:
        if i > curr + 4:
            res += 1
            curr = i
    return res
```

<hr>

## **90. Cavity Map**

```py

def cavityMap(grid):
    # Write your code here
    res = []
    for i in range(len(grid)):
        if i == 0 or i == len(grid)-1:
            res.append(grid[i])
        else:
            temp = ""
            for j in range(len(grid[i])):
                if j == 0 or j == len(grid[i])-1:
                    temp += grid[i][j]
                else:
                    if grid[i][j] > grid[i-1][j] and grid[i][j] > grid[i+1][j] and grid[i][j] > grid[i][j-1] and grid[i][j] > grid[i][j+1]:
                        temp += "X"
                    else:
                        temp += grid[i][j]
            res.append(temp)
    return res
```

<hr>

## **91. Strange Counter**

```py

def strangeCounter(t):
    # Write your code here
    res = 3
    while t > res:
        t -= res
        res *= 2
    return res - t + 1
```

<hr>

## **92. Insertion Sort - Part 1**

```py

def insertionSort1(n, arr):
    # Write your code here
    temp = arr[-1]
    for i in range(n-2, -1, -1):
        if arr[i] > temp:
            arr[i+1] = arr[i]
            print(*arr)
        else:
            arr[i+1] = temp
            print(*arr)
            break
    else:
        arr[0] = temp
        print(*arr)
```

<hr>

## **93. Making Anagrams**

```py

def makingAnagrams(s1, s2):
    s1 = list(s1)
    s2 = list(s2)
    i = 0
    while i < len(s1):
        if s1[i] in s2:
            s2.remove(s1[i])
            s1.remove(s1[i])
            continue
        i += 1
    return len(s1) + len(s2)
```

<hr>

## **94. Correctness and the Loop Invariant**

```py
def insertion_sort(l):
    for i in range(len(l)-1):
        j = i
        #key = l[i]
        while (j >= 0) and (l[j] > l[j+1]):
           l[j+1],l[j] = l[j],l[j+1]
           j -= 1
        #l[j+1] = key
    

m = int(input().strip())
ar = [int(i) for i in input().strip().split()]
insertion_sort(ar)
print(" ".join(map(str,ar)))
```

<hr>

## **95. Running Time of Algorithms**

```py

def runningTime(arr):
    # Write your code here
    res = 0
    for i in range(1, len(arr)):
        temp = arr[i]
        j = i - 1
        while j >= 0 and temp < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
            res += 1
        arr[j+1] = temp
    return res
```

<hr>

## **96. Insertion Sort - Part 2**

```py

def insertionSort2(n, arr):
    # Write your code here
    for i in range(1, n):
        temp = arr[i]
        j = i - 1
        while j >= 0 and temp < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = temp
        print(*arr)
```

<hr>

## **97. Intro to Tutorial Challenges**

```py

def introTutorial(V, arr):
    # Write your code here
    return arr.index(V)
```

<hr>

## **98. Counting Sort 2**

```py

def countingSort(arr):
    # Write your code here
    res = [0]*100
    for i in arr:
        res[i] += 1
    return [i for i in range(100) for j in range(res[i])]
```

<hr>

## **99. Manasa and Stones**

```py

def stones(n, a, b):
    # Write your code here
    res = set()
    for i in range(n):
        res.add(i*a + (n-i-1)*b)
    return sorted(res)
```

<hr>

## **100. Largest Permutation**

```cpp

//cpp
vector<int> largestPermutation(int k, vector<int> arr) {
    int swaps = 0;
    for (int i = 0; swaps < k && i < arr.size(); i++)
    {
        int expected = arr.size() - i;
        if (arr[i] != expected)
        {
            auto item = std::find(arr.begin() + i + 1, arr.end(), expected);
            std::iter_swap(arr.begin() + i, item);
            swaps++;
        }
    }
    return arr;
}
```

<hr>

## **101. Mark and Toys**

```py

def maximumToys(prices, k):
    # Write your code here
    prices.sort()
    res = 0
    for i in prices:
        if k >= i:
            res += 1
            k -= i
        else:
            break
    return res
```

<hr>

## **102. Closest Numbers**

```py

def closestNumbers(arr):
    # Write your code here
    arr.sort()
    res = []
    min_diff = arr[1] - arr[0]
    for i in range(1, len(arr)-1):
        if arr[i+1] - arr[i] < min_diff:
            min_diff = arr[i+1] - arr[i]
    for i in range(len(arr)-1):
        if arr[i+1] - arr[i] == min_diff:
            res.append(arr[i])
            res.append(arr[i+1])
    return res
```

<hr>

## **103. Find the Median**

```py

def findMedian(arr):
    # Write your code here
    arr.sort()
    return arr[len(arr)//2]
```

<hr>

## **104. Sherlock and Array**

```py

def balancedSums(arr):
    # Write your code here
    left = 0
    right = sum(arr)
    for i in arr:
        right -= i
        if left == right:
            return "YES"
        left += i
    return "NO"
```

<hr>

## **105. Flipping bits**

```py

def flippingBits(n):
    # Write your code here
    return n ^ 0xFFFFFFFF
```

<hr>

## **106. Jim and the Orders**

```py

def jimOrders(orders):
    # Write your code here
    res = []
    for i in range(len(orders)):
        res.append([i+1, orders[i][0]+orders[i][1]])
    res.sort(key=lambda x: x[1])
    return [i[0] for i in res]
```

<hr>

## **107. Permuting Two Arrays**

```py

def twoArrays(k, A, B):
    # Write your code here
    A.sort()
    B.sort(reverse=True)
    for i in range(len(A)):
        if A[i] + B[i] < k:
            return "NO"
    return "YES"
```

<hr>

## **108. Missing Numbers**

```py

def missingNumbers(arr, brr):
    # Write your code here
    res = []
    for i in set(brr):
        if brr.count(i) != arr.count(i):
            res.append(i)
    return sorted(res)
```

<hr>

## **109. Forming a Magic Square**

```py

def formingMagicSquare(s):
    # Write your code here
    magic_squares = [
        [[8, 1, 6], [3, 5, 7], [4, 9, 2]],
        [[6, 1, 8], [7, 5, 3], [2, 9, 4]],
        [[4, 9, 2], [3, 5, 7], [8, 1, 6]],
        [[2, 9, 4], [7, 5, 3], [6, 1, 8]],
        [[8, 3, 4], [1, 5, 9], [6, 7, 2]],
        [[4, 3, 8], [9, 5, 1], [2, 7, 6]],
        [[6, 7, 2], [1, 5, 9], [8, 3, 4]],
        [[2, 7, 6], [9, 5, 1], [4, 3, 8]],
    ]
    min_cost = 100
    for magic_square in magic_squares:
        cost = 0
        for i in range(3):
            for j in range(3):
                cost += abs(s[i][j] - magic_square[i][j])
        min_cost = min(min_cost, cost)
    return min_cost
```

<hr>

## **110. Climbing the Leaderboard**

```py
def climbingLeaderboard(ranked, player):
    # Write your code here
    unique_rank = sorted(list(set(ranked)), reverse=True)

    rank_result = []
    for score in player:
        while len(unique_rank) > 0 and score >= unique_rank[-1]:
            unique_rank.pop()

        rank_result.append(len(unique_rank) + 1)
    
    return rank_result
```

<hr>

## **111. The Time in Words**

```py

def timeInWords(h, m):
    # Write your code here
    words = ["one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten", "eleven", "twelve", "thirteen", "fourteen", "quarter", "sixteen", "seventeen", "eighteen", "nineteen", "twenty", "twenty one", "twenty two", "twenty three", "twenty four", "twenty five", "twenty six", "twenty seven", "twenty eight", "twenty nine", "half"]
    if m == 0:
        return words[h-1] + " o' clock"
    elif m == 1:
        return words[m-1] + " minute past " + words[h-1]
    elif m == 15 or m == 30:
        return words[m-1] + " past " + words[h-1]
    elif m < 30:
        return words[m-1] + " minutes past " + words[h-1]
    elif m == 59:
        return words[60-m-1] + " minute to " + words[h]
    elif m == 45:
        return words[60-m-1] + " to " + words[h]
    else:
        return words[60-m-1] + " minutes to " + words[h]
```

<hr>

## **112. Organizing Containers of Balls**

```py

def organizingContainers(container):
    # Write your code here
    row_sum = [sum(i) for i in container]
    col_sum = [sum(i) for i in zip(*container)]
    return "Possible" if sorted(row_sum) == sorted(col_sum) else "Impossible"
```

<hr>

## **113. Encryption**

```py

def encryption(s):
    # Write your code here
    s = s.replace(" ", "")
    row = math.floor(math.sqrt(len(s)))
    col = math.ceil(math.sqrt(len(s)))
    if row * col < len(s):
        row += 1
    res = ""
    for i in range(col):
        for j in range(row):
            if i + j * col < len(s):
                res += s[i + j * col]
        res += " "
    return res
```

<hr>

## **114. Sansa and XOR**

```py

def sansaXor(arr):
    # Write your code here
    if len(arr) % 2 == 0:
        return 0
    else:
        res = 0
        for i in range(0, len(arr), 2):
            res ^= arr[i]
        return res
```

<hr>

## **115. Recursive Digit Sum**

```py

def superDigit(n, k):
    # Write your code here
    if len(n) == 1:
        return n
    else:
        return superDigit(str(sum([int(i) for i in n]) * k), 1)
```

<hr>

## **116. The Grid Search**

```py

def gridSearch(G, P):
    # Write your code here
    for i in range(len(G) - len(P) + 1):
        for j in range(len(G[0]) - len(P[0]) + 1):
            if G[i][j] == P[0][0]:
                for k in range(len(P)):
                    if G[i+k][j:j+len(P[0])] != P[k]:
                        break
                else:
                    return "YES"
    return "NO"
```

<hr>

## **117. Flipping the Matrix**

```py

def flippingMatrix(matrix):
    # Write your code here
    n = len(matrix) // 2
    res = 0
    for i in range(n):
        for j in range(n):
            res += max(matrix[i][j], matrix[i][2*n-1-j], matrix[2*n-1-i][j], matrix[2*n-1-i][2*n-1-j])
    return res
```

<hr>

## **118. Counter game**

```py

def counterGame(n):
    # Write your code here
    turn = 0
    while n > 1:
        if n & (n-1) == 0:
            n //= 2
        else:
            n -= 2 ** (n.bit_length() - 1)
        turn += 1
    return "Richard" if turn % 2 == 0 else "Louise"
```

<hr>

## **119. Max Min**

```py

def maxMin(k, arr):
    # Write your code here
    arr.sort()
    res = arr[-1]
    for i in range(len(arr) - k + 1):
        res = min(res, arr[i+k-1] - arr[i])
    return res
```

<hr>

## **120. Greedy Florist**

```py

def getMinimumCost(k, c):
    # Write your code here
    c.sort(reverse=True)
    res = 0
    for i in range(len(c)):
        res += (i // k + 1) * c[i]
    return res
```

<hr>

## **121. Sherlock and the Valid String**

```cpp
//cpp
string isValid(string s) {
    map<char, int> occ;
    map<int, int> mp;
    for(char c: s) occ[c]++;
    for(auto it = occ.begin(); it != occ.end(); it++) mp[it->second]++;
    if(mp.size() == 1) return "YES";
    cout << mp.size() << endl;
    if(mp.size() == 2){
        int fk = mp.begin()->first, fv = mp.begin()->second, sk = next(mp.begin())->first , sv = next(mp.begin())->second;
        if((fk == 1 && fv == 1) || (sk == 1 && sv == 1)) return "YES";
        if((fk - sk == 1 && fv == 1) || (sk - fk == 1 && sv == 1)) return "YES";
    }
    return "NO";
}
```

## **121. Gaming Array**

```java
//java
public static String gamingArray(List<Integer> arr) {
    // Write your code here
        int max = -1;
        int steps = 0;
        
        for(int i = 0; i < arr.size(); i++){
            if(arr.get(i) > max){
                max = arr.get(i);
                steps++;
            }
        }
        
        if(steps % 2 == 0) return "ANDY";
        else return "BOB";
    }
```

