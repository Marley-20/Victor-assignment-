#include <stack>

class Solution {
public:
    ListNode* addTwoNumbers(ListNode* left, ListNode* right) {
        std::stack<int> digitsLeft;
        std::stack<int> digitsRight;

        while (left != nullptr) {
            digitsLeft.push(left->val);
            left = left->next;
        }
        while (right != nullptr) {
            digitsRight.push(right->val);
            right = right->next;
        }

        int carry = 0;
        ListNode* answer = nullptr;

        while (!digitsLeft.empty() || !digitsRight.empty() || carry > 0) {
            int total = carry;

            if (!digitsLeft.empty()) {
                total += digitsLeft.top();
                digitsLeft.pop();
            }
            if (!digitsRight.empty()) {
                total += digitsRight.top();
                digitsRight.pop();
            }

            ListNode* current = new ListNode(total % 10);
            current->next = answer;
            answer = current;
            carry = total / 10;
        }

        return answer;
    }
};
