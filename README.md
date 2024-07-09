# SortPackages

public class PackageSorter {

    public static String sort(int width, int height, int length, int mass) {
        // Calculate volume
        long volume = (long) width * height * length;
        
        // Determine if the package is bulky
        boolean isBulky = volume >= 1000000 || width >= 150 || height >= 150 || length >= 150;
        
        boolean isHeavy = mass >= 20;// Determine if the package is heavy

       //Categorize the package
        if (isBulky && isHeavy) {
            return "REJECTED";
        } else if (isBulky || isHeavy) {
            return "SPECIAL";
        } else {
            return "STANDARD";
        }
    }
}

      // Test cases
        System.out.println(sort(100, 100, 100, 10));  // Output: STANDARD
        System.out.println(sort(200, 50, 50, 10));    // Output: SPECIAL (bulky)
        System.out.println(sort(100, 100, 100, 25));  // Output: SPECIAL (heavy)
        System.out.println(sort(200, 200, 200, 25));  // Output: REJECTED (bulky and heavy)



Explanation:

1.sort(width, height, length, mass) function:
Takes four integer arguments representing the package's dimensions (width, height, length) in centimeters and its mass in kilograms.
Returns a string indicating the stack where the package should be placed.

2. Calculating Bulkiness:
isBulky variable:
Checks if the volume (width * height * length) is greater than or equal to 1,000,000 cm³.
Checks if any of the dimensions (width, height, length) is greater than or equal to 150 cm.
If either condition is true, the package is considered bulky.

3.Calculating Heaviness:
isHeavy variable:
Checks if the mass is greater than or equal to 20 kg.

4.Determining the Stack:
REJECTED: If both isBulky and isHeavy are true, the package is rejected.
SPECIAL: If either isBulky or isHeavy is true, the package is placed in the SPECIAL stack.
STANDARD: If neither isBulky nor isHeavy is true, the package is placed in the STANDARD stack.
