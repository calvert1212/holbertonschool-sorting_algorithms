#include "sort.h"

/**
 * radix_sort - sorts and array using Radix algo
 * @array: array
 * @size: size of the array
 */
void radix_sort(int *array, size_t size)
{
	int m;
	size_t i, least;

	if (!array || size < 2)
		return;
	m = 0;
	for (i = 0; i < size; i++)
	{
		if (array[i] > m)
		{
			m = array[i];
		}
	}

	for (least = 1; m / least > 0; least *= 10)
	{
		lsd(array, size, least);
		print_array(array, size);
	}
}

/**
 * lsd - sort with lsd priority
 * @array: array passed from main
 * @size: array n size
 * @least: least significant digit
 */
void lsd(int *array, size_t size, size_t least)
{
	int c_arr[10] = {0};
	int *sort_out;
	int l, m;
	size_t k, n;

	sort_out = malloc(sizeof(int) * size);

	for (k = 0; k < size; k++)
	{
		c_arr[(array[k] / least) % 10] += 1;
	}
	for (l = 1; l < 10; l++)
	{
		c_arr[l] += c_arr[l - 1];
	}
	for (m = size - 1; m >= 0; m--)
	{
		sort_out[c_arr[(array[m] / least) % 10] - 1] = array[m];
		c_arr[(array[m] / least) % 10]--;
	}

	for (n = 0; n < size; n++)
		array[n] = sort_out[n];

	free(sort_out);
}
