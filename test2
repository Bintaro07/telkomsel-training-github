{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "private_outputs": true,
      "provenance": [],
      "toc_visible": true,
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/restupradewa/suka_lupa/blob/main/Restu_Galih_Pradewa_Module_3_Take_home_Assignment_Template.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "# Import Packages"
      ],
      "metadata": {
        "id": "XfYwSIvKvWQ8"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "import gdown"
      ],
      "metadata": {
        "id": "av1nJAoPtI-4"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "# Download Data"
      ],
      "metadata": {
        "id": "lnlnpGTUvUsQ"
      }
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "2J8FJ-M0s7c6"
      },
      "outputs": [],
      "source": [
        "gdrive_url_account = \"https://drive.google.com/file/d/1V6wfb5Je3tZSRq4-4UA50PTrheZXxIJr/view?usp=sharing\"\n",
        "file_name = 'telecom_account.csv'\n",
        "\n",
        "gdown.download(gdrive_url_account, file_name, fuzzy=True)\n",
        "\n",
        "gdrive_url_usage = \"https://drive.google.com/file/d/1MHGXp1AT4if4GiWLDGWnAqELGcb2FrtB/view?usp=drive_link\"\n",
        "file_name = 'telecom_usage.csv'\n",
        "\n",
        "gdown.download(gdrive_url_usage, file_name, fuzzy=True)"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "# Load Data"
      ],
      "metadata": {
        "id": "L9s_-pAKvYb6"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd"
      ],
      "metadata": {
        "id": "P3lcWWvXtm_1"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account = pd.read_csv('/content/telecom_account.csv')\n",
        "df_account.head()"
      ],
      "metadata": {
        "id": "9DO-s4gLtoSL"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_usage = pd.read_csv('/content/telecom_usage.csv')\n",
        "df_usage.head()"
      ],
      "metadata": {
        "id": "iuKomhfHxWJQ"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account.info()"
      ],
      "metadata": {
        "id": "-p_7MCuhtpi5"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account.nunique()"
      ],
      "metadata": {
        "id": "viOpwfeffsN7"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account['customer_gender'].value_counts()"
      ],
      "metadata": {
        "id": "wI4XeKivey7e"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "# Cleaning Customer Gender"
      ],
      "metadata": {
        "id": "Vz10RzvQvaT8"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "df_account[(df_account['customer_gender'].isin(['.','U']))].head()"
      ],
      "metadata": {
        "id": "XseJO5P_vkL_"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account[df_account['customer_gender'].isnull()].head()"
      ],
      "metadata": {
        "id": "rTxv3n4rmAs2"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account['customer_gender'].value_counts(dropna=False)"
      ],
      "metadata": {
        "id": "WhZQCb-JjU9A"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account.loc[(df_account['customer_gender'].isin(['.','U'])|df_account['customer_gender'].isnull())]='u'"
      ],
      "metadata": {
        "id": "pmm_65t8zV2T"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_account['customer_gender'].value_counts()"
      ],
      "metadata": {
        "id": "Km6QrdIXigIJ"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "# RFM Exploration"
      ],
      "metadata": {
        "id": "J86IhLHExAsL"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "df_usage = pd.read_csv('/content/telecom_usage.csv')"
      ],
      "metadata": {
        "id": "DN4STEk1wkib"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_usage.info([''])"
      ],
      "metadata": {
        "id": "qC4i-Zf4Z0Ku"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_usage.nunique()"
      ],
      "metadata": {
        "id": "S57GIK9PWg1o"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_usage.loc[:,['Customer_ID','mb_data_usg_m01','avg_arpu_3m','lifetime_value','rfm_score']]"
      ],
      "metadata": {
        "id": "te2TSduKagS-"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_rfm = df_usage.groupby('rfm_score').agg({'mb_data_usg_m01' : ['mean', 'max'] , 'avg_arpu_3m' : 'mean', 'lifetime_value' : 'mean'})\n",
        "df_rfm"
      ],
      "metadata": {
        "id": "gln530xPcBfa"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "# Merge Table"
      ],
      "metadata": {
        "id": "-qOT8hARyglf"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "df_account_selected = df_account.loc[:,['Customer_ID','customer_gender','region']]\n",
        "df_account_selected"
      ],
      "metadata": {
        "id": "ViV4THte0Jqc"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_usage_selected = df_usage.loc[:,['Customer_ID','mb_data_usg_m01','avg_arpu_3m','lifetime_value','rfm_score']]\n",
        "df_usage_selected"
      ],
      "metadata": {
        "id": "UgQCGlJY0O6N"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_join = df_account_selected.merge(df_usage_selected, on = 'Customer_ID')"
      ],
      "metadata": {
        "id": "-aPEyZUZ1Gvb"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "df_join.loc[df_join['Customer_ID'].isin ([84690, 3998832, 3999066])]"
      ],
      "metadata": {
        "id": "gliFiA89iXw5"
      },
      "execution_count": null,
      "outputs": []
    }
  ]
}
