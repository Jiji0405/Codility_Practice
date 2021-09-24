import java.util.Arrays;

public class CountingElements {
    // 1
    public int frogRiverOne(int X, int[] A) {
        int result = -1;
        int len = A.length;
        if (len >= X) {
            int[] dp = new int[X + 1];
            for (int i = 1; i < X; i++) {
                dp[i] = 1;
            }

            for (int i = 0; i < len; i++) {
                int idx = A[i];
                if (dp[idx] == 1) {
                    dp[idx] = 0;
                    X -= 1;
                }

                if (X == 0) {
                    result = idx;
                    break;
                }
            }
        }
        return result;
    }

    // 2
    public static int permCheck(int[] A) {
        int len = A.length;
        Arrays.sort(A);
        if (A[0] != 1) {
            return 0;
        }

        for (int i = 1; i < len; i++) {
            int bit = A[i]^(i+1);
            if (bit != 0) {
                return 0;
            }
        }
        return 1;
    }

    // 3
    static int[] counters;
    public static int[] maxCounters(int N, int[] A) {
        counters = new int[N];
        for(int i = 0; i < N; i++) {
            counters[i] = 0;
        }

        int max = 0;
        int startNum = max;
        for (int val : A) {
            if (val == N + 1) {
                startNum = max;
            } else {
                if (counters[val - 1] < startNum) {
                    counters[val - 1] = (startNum + 1);
                } else {
                    counters[val - 1] += 1;
                }
                max = Math.max(max, counters[val - 1]);
            }
        }

        for (int i = 0; i < counters.length; i++) {
            if (counters[i] < startNum) {
                counters[i] = startNum;
            }
        }
        return counters;
    }
}
