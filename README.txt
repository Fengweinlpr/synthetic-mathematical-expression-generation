0. color_tex.tex �Ǳ���ɫ��tex��ʽ�б�, ������linux�����ɹ�ʽͼ��
1. color-list.txt �Ǹ���Hͨ��������ɫ֮���Ӧ��rbgͨ����ֵ
2. generate_formula.m �����ɵ�����ʽ�ĺ���
3. get_formulas.m ������color_tex.tex�ļ��ĺ���, ���д������ɫ�Ĺ�ʽ
4. hsvread.m ��tex2im���ɵ�ͼ��תΪhsv��ʽ�ĺ���
5. parsing_by_config.m ����parsing��ͼ��, �ļ��������ŷ���
6. regular_teximages.m ��linux���ɵ�ͼ�񶼹�һ����ͬһ���ֱ��� -> ������regular_imageformat.m
7. set_symbol_color.m ����ʽ��ɫ
8. sort_used_set.m ѡȡ���ż�
9. get_color_label_list.m ����color-list.txt �� label-list.txt
10. get_caffe_data.m ���ɻҶ�ͼ��, �Լ�label
11. expand_samples.m �����ɵ�ͼ�����ǩ��������
12. distort_formulas.m �Բ�ɫ��ʽͼ������Ŷ�
13. expand_labels.m ��label��������, ����multi-task��һ��label-channel
14. extract_origin_boundingbox.m ��ԭͼ�ķ��Ž���bounding_box����ȡ, �����ĸ���������Լ�labelֵ
15. 

# ʹ������
. ����get_color_label_list ����color-list.txt �� label-list.txt
. ��label-list.txt ���������з��ŵ�list, Ȼ����operater-list.txt �������������list
. ����get_formulas �õ�color_tex.tex
. ��linux�����ɲ�ɫ�Ĺ�ʽͼ��
. ����regular_imageformat, ͳһͼ��ĸ�ʽ #����regular_teximages ��һ���ֱ���
. ����extract_origin_boundingbox, ��ȡbounding-box

+ parsing:
. ����distort_formulas, �Բ�ɫͼ������Ŷ�
. ����parsing_by_config ����labelͼ��
. ����get_caffe_data ���ɻҶ�ͼ��label, Ĭ�����ɶ�ֵͼ
. ����expand_labels �������͵�label, ����ǰ��Ҫ��ǰ�趨uncare_label��ֵ
. �����Ҫ, ����expand_samples �������ͺ������
 
+ densebox: (prepare_densebox_data_from_image.m ������ִ������Ľű�)
. ����adjust_boundingbox.m, ����ĳЩ����bounding-box
. ����distort_formulas, �Բ�ɫͼ������Ŷ�
. ����parsing_by_config ����labelͼ��
. ����get_caffe_data ���ɻҶ�ͼ��label, Ĭ�����ɶ�ֵͼ
. ����get_caffe_densebox_data.m, ����ѵ��densebox����Ҫ������
 
# ��������̻��ܼ�, parsing_by_config.m ����ֱ�����ɴ�label��Ϣ��ͼ��
# �Ż� 2015 07 07 �Ż��˹�ʽ���ȵĿ��Ʋ���, ���������ɼ����߳��Ĺ�ʽ
# 2015 07 10 ���һ�����������͵�label��image
# 2015 07 14 �ḻ���ż���, ��һ���Ż���ʽ���ȵļ���
# 2015 07 14 ��get_caffe_data ����ӻҶ�ͼ�ӿ�
# 2015 07 15 �޸���Hͨ���������ش�bug, ��HSV��������RGBʱHͨ������ֵΪ1
# 2015 07 19 �����˷�ʽ��ѡ��
# 2015 07 20 �޸�regular_teximages�����й�һ������, �����ⲽ��������Ϊregular_imageformat
# 2015 07 20 ���distort_formulas.m �Բ�ɫͼ������Ŷ�
# 2015 07 21 �޸�regular_imageformat, ���ɺڵ�ͼ��, �����ͺ�ʴ������������ʵ����
# 2015 07 22 �޸�distort_formulas, ���м���, ���ٷ���20������
# 2015 07 22 �޸�get_caffe_data, �Ҷ�ͼ�ı������ɷ������ֳɵı���ͼ
# 2015 07 22 �޸�get_caffe_data, �ò�ɫͼ������, ������jpg��ʽ�洢, ��ɫ�ֲʵ�
# 2015 07 24 ���expand_labels �������͵�label
# 2015 07 26 ���expand_labels, �Լ������Ż�, ����ǰ��Ҫ��ǰ�趨uncare_label��ֵ
# 2015 07 30 ���extract_origin_boundingbox
# 2015 07 30 �޸�get_formula, ���ɵ�tex_i.config�ļ�������ֵ���� label h_value
# 2015 07 31 �޸�distort_formulas, �����α���bounding-box����
# 2015 07 31 �޸�get_caffe_data, ����center-label����
# 2015 07 31 �޸�parsing_by_config, ����д��ô������
# 2015 08 09 ��������ӵ���94��
# 2015 09 09 �������Ƴ�pair_set, �������ŵ���������һ�����Ŵ���, ɾ��long arrow, �����Ϊ95��
# 2015 09 09 �޸�extract_origin_boundingbox, ��i j �������������еĵ������⴦��
# 2015 10 07 �޸�������extract_origin_boundingbox ���i j = >= <= �� �� �� ... :�������⴦��, ����˼·���ǽ���ƥ��˼·
# 2015 10 07 �޸������ŵ���ɫ����, �������ŵ���ɫ��ͬ, ������Ϊһ�������ļ���, ���������ɹ�ʽ����ʱ���pair_set����һ��
# 2015 10 07 �Ż��˹�ʽ���ɲ���, ����һ�����и��ʳ���, ��ĸȡһ���ֳ���
# 2015 10 08 �޸���get_caffe_data ���յ�labelmap, centerlabel �ֱ���������, ����һ���ǽ��ֱ��ʵ�
# 2015 10 08 �޸��˹�ʽ���ɵ�����, ��ҪԤ���޸�����txt�ļ�: label-list.txt & operater-list.txt
# 2015 10 10 ������regular_imageformat, ����lib��forѭ��
# 2015 10 12 �޸���distort_formulas, ������global_scale�ı�����������ͼ��DPI̫�����������, ��С����б�ķ�Χ
# 2015 10 15 add gray_contrast into get_caffe_data
# 2015 10 15 add get_caffe_mulcls_densebox_data.m to generate multi-class gt 
# 2015 10 26 refine the for loop
# 2016 04 26 refine the bounding box of sqrt symbol in 'extract_origin_boundingbox.m'



