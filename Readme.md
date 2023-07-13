# PPT - DSA Assignment 04

<br/>

## Answer 1:
```js
const findCommonNumber = (ar1, ar2, ar3) => {

    let n1 = ar1.length;
    let n2 = ar2.length;
    let n3 = ar3.length;

    // Initialize starting indexes
    let i = 0;
    let j = 0;
    let k = 0;

    // Iterate through three arrays
    while (i < n1 && j < n2 && k < n3) {
        // If x = y and y = z, print any of them and move ahead in all arrays
        if (ar1[i] == ar2[j] && ar2[j] == ar3[k]) {
            console.log(ar1[i] + " ");
            i++;
            j++;
            k++;
        }

        // x < y
        else if (ar1[i] < ar2[j])
            i++;

        // y < z
        else if (ar2[j] < ar3[k])
            j++;

        // We reach here when x > y and z < y, i.e., z is smallest
        else
            k++;
    }
}
```

<br/>

## Answer 2:
```js
const findDifference = (nums1, nums2) => {
    let set1 = new Set(nums1),
        set2 = new Set(nums2);

    let a = [],
        b = [];
    for (let e of set1) if (!set2.has(e)) a.push(e);
    for (let e of set2) if (!set1.has(e)) b.push(e);

    return [a, b];
};
```

<br/>

## Answer 3;
```js
const transpose = (matrix) => {
    let result = [];
    let row = matrix.length;
    let col = matrix[0].length;
    for (let i = 0; i < row; i++) {
        for (let j = 0; j < col; j++) {
            if (!result[j]) {
                result[j] = [];
            }
            result[j][i] = matrix[i][j];
        }
    }
    return result;
};
```

<br/>

## Answer 4:
```js
const pairArrays = (nums) => {
    nums.sort((a, b) => a - b)
    let sum = 0;
    for (let i = 0; i < nums.length; i += 2) {
        sum += nums[i]
    }
    return sum;
};
```

<br/>

## Answer 5:
```js
const arrangeCoins = (n) => {
    let count = 0;
    for (let i = 1; i <= n; i++) {
        n = n - i;
        count++;
    }
    return count;
};
```

<br/>

## Answer 6:
```js
// Two pointer
const sortedSquares = (nums) => {
    let result = [];
    // Left and right pointer
    let l = 0;
    let r = nums.length - 1;
    // Position to add squared number to A
    let p = r;

    // Add the higher number to the array and then decrease the pointer
    while (l <= r) {
        if (nums[l] ** 2 > nums[r] ** 2) {
            result[p--] = nums[l++] ** 2;
        } else {
            result[p--] = nums[r--] ** 2;
        }
    }

    return result;
};
```

<br/>

## Answer 7:
```js
const countMax = (m, n, ops) => {
    for (let i = 0, len = ops.length; i < len; i++) {
        if (ops[i][0] < m) {
            m = ops[i][0];
        }
        if (ops[i][1] < n) {
            n = ops[i][1];
        }
    }
    return m * n;
}
```

<br/>

## Answer 8:
```js
const arrangeArray = (nums, n) => {
    let res = [];
    for (let i = 0; i < n; i++) {
        res.push(nums[i], nums[i + n]);
    }
    return res;
};
```