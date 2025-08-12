# Print-matrix-in-spiral-form
def spiral_print(matrix):
    if not matrix:
        return
    
    top, bottom = 0, len(matrix) - 1
    left, right = 0, len(matrix[0]) - 1
    
    while top <= bottom and left <= right:
        # Traverse from Left to Right
        for i in range(left, right + 1):
            print(matrix[top][i], end=" ")
        top += 1
        
        # Traverse from Top to Bottom
        for i in range(top, bottom + 1):
            print(matrix[i][right], end=" ")
        right -= 1
        
        # Traverse from Right to Left
        if top <= bottom:
            for i in range(right, left - 1, -1):
                print(matrix[bottom][i], end=" ")
            bottom -= 1
        
        # Traverse from Bottom to Top
        if left <= right:
            for i in range(bottom, top - 1, -1):
                print(matrix[i][left], end=" ")
            left += 1

# Example usage:
matrix = [
    [1, 2, 3, 4],
    [5, 6, 7, 8],
    [9, 10, 11, 12],
    [13, 14, 15, 16]
]
spiral_print(matrix)
