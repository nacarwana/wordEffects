//

#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    @autoreleasepool {
        
        char inputChars[255];
        int inputNum;
        
        while(YES) {
        
            printf("Input a string: ");
            fgets(inputChars, 255, stdin);
            
            printf("1. Uppercase\n2. Lowercase\n3. Numberize\n4. Canadianize\n5. Respond\n6. De-Space-It\n\n");
            
            printf("Input a number: ");
            scanf(" %d", &inputNum);
            getchar();
            
            printf("You Chose Number %d\n", inputNum);
            
            printf("Your string is %s\n", inputChars);
         
            
            
            NSString *inputString = [NSString stringWithUTF8String:inputChars];

            
            switch (inputNum) {
                case 1:
                    inputString = [inputString uppercaseString];
                    break;
                case 2:
                    inputString = [inputString lowercaseString];
                    break;
                case 3:
                    //inputString = [numberFromString:@"42"];
                    break;
                case 4:
                    inputString = [inputString stringByAppendingString:@", eh?"];
                    break;
                case 5:
                    if ([inputString hasSuffix:@"?\n"]) {
                        inputString = @"I don't know\n";
                    } else if ([inputString hasSuffix:@"!\n"]) {
                        inputString = @"Whoa, calm down!\n";
                    }
                    break;
                case 6:
                    inputString = [inputString stringByReplacingOccurrencesOfString:@" " withString:@"-"];
                    break;
                default:
                    break;
            }

            
                    NSLog(@"\nOutput is: %@\n", inputString);
        }

        
    }
    return 0;
}
