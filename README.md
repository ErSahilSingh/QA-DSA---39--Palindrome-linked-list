# QA-DSA---39--Palindrome-linked-list

/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {boolean}
 */
var isPalindrome = function(head) {
    //find middle elemet
    let slow =head
    let fast=head
    while(fast && fast.next){
        slow=slow.next
        fast= fast.next.next
    }

    //revers half element
   let prev=null
   let curr=slow
   while(curr){
    let temp=curr.next
    curr.next=prev
    prev=curr
    curr=temp
   }

   //check palidrom

   let firstlist=head
   let secondlist=prev

   while(secondlist){
    if(firstlist.val != secondlist.val){
        return false
    }
    firstlist=firstlist.next
    secondlist=secondlist.next
   }
    return true
};
