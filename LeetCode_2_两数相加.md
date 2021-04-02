```C#
/*
 * 2.两数相加
 * 
 * 给出两个 非空 的链表用来表示两个非负的整数。其中，它们各自的位数是按照 逆序 的方式存储的，并且它们的每个节点只能存储 一位 数字。
 * 如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。
 * 您可以假设除了数字 0 之外，这两个数都不会以 0 开头。
 * 
 * 示例：
 * 输入：(2 -> 4 -> 3) + (5 -> 6 -> 4)
 * 输出：7 -> 0 -> 8
 * 原因：342 + 465 = 807
 * 
 * Definition for singly-linked list. （单一节点的链表的定义）
 * public class ListNode {
 *     public int val;
 *     public ListNode next;
 *     public ListNode(int val=0, ListNode next=null) {
 *         this.val = val;
 *         this.next = next;
 *     }
 * }
 */

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LeetCode_2
{
    class Program
    {
        
        static void Main(string[] args)
        {
            ListNode listNode1_1 = new ListNode(2);
            ListNode listNode1_2 = new ListNode(4);
            listNode1_1.next = listNode1_2;
            ListNode listNode1_3 = new ListNode(3);
            listNode1_2.next = listNode1_3;
            ListNode[] listNodes1 = new ListNode[] { listNode1_1, listNode1_2, listNode1_3 };

            ListNode listNode2_1 = new ListNode(8);
            ListNode listNode2_2 = new ListNode(6);
            ListNode listNode2_3 = new ListNode(4);
            listNode2_1.next = listNode2_2;
            listNode2_2.next = listNode2_3;
            ListNode[] listNodes2 = new ListNode[] { listNode2_1, listNode2_2, listNode2_3 };

            ListNode ResultListNode1 = new ListNode(0);
            ListNode ResultListNode2 = new ListNode(0);
            ListNode ResultListNode3 = new ListNode(0);
            ListNode[] ResultListNodes = new ListNode[] { ResultListNode1, ResultListNode2, ResultListNode3 };

            for (int count = 0; count < 3; count++)
            {
                ResultListNodes[count].value += (listNodes1[count].value + listNodes2[count].value) % 10;
                if ((listNodes1[count].value + listNodes2[count].value) >= 10)
                {
                    ResultListNodes[count + 1].value += 1;
                }
            }

            Console.WriteLine(ResultListNodes[0].value + " " + ResultListNodes[1].value + " " + ResultListNodes[2].value);
            Console.ReadLine();
        }
    }

    public class ListNode
    {
        public int value;
        public ListNode next;
        public ListNode(int val)
        {
            value = val;
        }
    }
    
}
```
