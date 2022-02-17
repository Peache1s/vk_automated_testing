import pytest


test_list1 = []
test_dict1 = {}
test_list2 = ["re", 3, 4]
test_dict2 = {"re": "val1", 2: "val2", "3": "val3"}


def test_list_empty():
    assert test_list1 == []


def test_dict_empty():
    assert test_dict1 == {}


@pytest.mark.parametrize("t_list, expected_result", [([], []), ([1], [1]), ([1, 2, 3, 4],
                                                    [1, 2, 3, 4]), ([3, 2, 4, 1], [1, 2, 3, 4]),
                                                    ([2, 2, 4, 2], [2, 2, 2, 4])
                                                     ])
def test_list_sort(t_list, expected_result):
    assert sorted(t_list) == expected_result


def test_list_to_number():
    try:
        assert list(map(int, test_list2))
    except ValueError:
        pass


def dict_pos(s_dict):

    for key in s_dict:
        if key <= 0:
            return 0
    return 1


@pytest.mark.parametrize("t_dict, expected_result", [({}, 1), ({-1: "val1"}, 0), ({-1: "val1", -2: 'val2'}, 0),
                                                     ({1: "val1"}, 1), ({1: "val1", -2: 'val2'}, 0),
                                                     ({0: "val1"}, 0)])
def test_positive(t_dict, expected_result):
    assert dict_pos(t_dict) == expected_result


def test_dict_to_number():
    try:
        list_of_keys = list(test_dict2.keys())
        assert list(map(int, list_of_keys))
    except ValueError:
        pass
