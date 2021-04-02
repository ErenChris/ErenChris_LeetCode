```C#
/*
 * 1. 两数之和
 * 
 * 给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。
 * 你可以假设每种输入只会对应一个答案。但是，数组中同一个元素不能使用两遍。
 * 
 * 示例:
 * 给定 nums = [2, 7, 11, 15], target = 9
 * 因为 nums[0] + nums[1] = 2 + 7 = 9
 * 所以返回 [0, 1]
 */

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LeetCode
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] result = new int[2] { 0, 0 };
            LeetCode1 example = new LeetCode1();
            result = example.TwoSum(example.exampleNumbers, example.target);
            Console.WriteLine($"下标为：{result[0]}和{result[1]}");
            Console.ReadLine();
        }
    }

    public class LeetCode1
    {
        public int[] exampleNumbers = new int[] { 2, 11, 8, 15 ,7};
        public int target = 9;
        public int[] errorNum = new int[] { 0 };

        public int[] TwoSum(int[] nums, int target)
        {
            for (int i = 0; i < nums.Length; i++)
            {
                for (int j = 0; j < nums.Length - 1; j++)
                {
                    if (nums[i] + nums[j] == target)
                    {
                        int[] RT = new int[2] { i, j };
                        return RT;
                    }

                }
            }
            return errorNum;
        }
    }
}
```
